
<?php
// Color definitions (ANSI escape codes)
$bold = "\033[1m";          // Bold text
$fverde = "\033[32m";       // Green foreground
$lverdebg = "\033[102m";    // Light green background
$amarelo = "\033[93m";      // Yellow foreground
$lamarelobg = "\033[103m";  // Light yellow background
$lazul = "\033[36m";        // Light blue foreground
$azul = "\033[34m";         // Blue foreground
$cln = "\033[0m";           // Reset colors
$branco = "\033[97m";       // White foreground
$vermelho = "\033[91m";     // Red foreground
$preto = "\033[30m\033[1m"; // Black bold
$ciano = "\033[36m";        // Cyan foreground
$magenta = "\033[35m";      // Magenta foreground
$azulbg = "\033[44m";       // Blue background
$lazulbg = "\033[106m";     // Light blue background
$verdebg = "\033[42m";      // Green background
$vermelhobg = "\033[101m";  // Red background
$cinza = "\033[37m";        // Gray foreground
$laranja = "\033[38;5;208m";// Orange foreground

echo $bold . $azul . "
    +---------------------------------------------+
    +             Farm     Menu                   +
    +---------------------------------------------+
\n\n";

sleep(5);

function farm_banner() {
    echo "\033[37m
          Farm Android \033[36mFucking Cheaters\033[91m\033[37m discord.gg/farmapostas
          
               )       (       (        (
            ) /( (   )\ )    )\ ) (    )\ )
           ( ((_)))\ (()/(   (()/( )\  (()/(
            )\ _ ((_) /(_))_  /(_)|(_) )(_))
           (_)_\((_)_(_)) __|(_)) _ _ (_))  
            / _ \| '_ \) |_  / __| | |/ __| 
           /_/ \_\_||_|\___|\___|_|\_\___| 
                                          

          {C} Coded By - Farm Apostas | Credits for Sheik        
          \033[32m
    ";
}

function inputusuario($message) {
    global $branco, $bold, $verdebg, $vermelhobg, $azulbg, $cln, $lazul, $fverde;
    $amarelobg = "\033[100m";
    $inputstyle = $cln . $bold . $lazul . "[#] " . $message . ": " . $fverde;
    echo $inputstyle;
}

function atualizar() {
    global $cln, $bold, $fverde;
    echo "\n\033[91m\033[1m[+] Farm Updater [+]
Atualizando, por favor aguarde...
{$cln}";
    system("git fetch origin && git reset --hard origin/master && git clean -f -d");
    echo $bold . $fverde . "[i] Atualização concluída! Por favor reinicie o Scanner \n" . $cln;
    die();
}

escolheropcoes:
system("clear");
farm_banner();

echo $amarelo . 
    " [0]  Instalar Módulos{$branco} (Atualizar e instalar módulos){$fverde} 
 [1]  Escanear FreeFire Normal 
 [2]  Escanear FreeFire Max 
 {$vermelho}[S]  Sair \n" . $cln;

inputusuario("Escolha uma das opções acima");
$MatarPresidentescanner = trim(fgets(STDIN, 1024));

if (!in_array($MatarPresidentescanner, ["0", "1", "2", "S"], true)) {
    echo $bold . $vermelho . "\n[!] Opção inválida! Tente novamente.\n\n" . $cln;
    goto escolheropcoes;
} else {
    if ($MatarPresidentescanner == "0") {
        atualizar();
    } elseif ($MatarPresidentescanner == "1") {
        system("clear");
        farm_banner();
        
        if (!shell_exec("adb version > /dev/null 2>&1")) {
            system("pkg install adb -y > /dev/null 2>&1");
        }
        
        date_default_timezone_set("America/Sao_Paulo");
        shell_exec("adb start-server > /dev/null 2>&1");
        
        $ApagarDadosDoDispositivoHackDispositivos = shell_exec("adb devices");
        if (empty($ApagarDadosDoDispositivoHackDispositivos) || 
            strpos($ApagarDadosDoDispositivoHackDispositivos, "device") === false) {
            echo $bold . $vermelho . "[!] Faça o pareamento de ip, cancelando telegam..\n\n";
            die();
        }
        
        $ApagarDadosDoDispositivoHackff = shell_exec("adb shell pm list packages | grep com.dtsearch.free");
        if (empty($ApagarDadosDoDispositivoHackff) || 
            strpos($ApagarDadosDoDispositivoHackff, "com.dtsearch.free") === false) {
            echo $bold . $vermelho . "[!] Freegram não instalado, cancelando..\n\n";
            die();
        }
        
        $ApagarDadosDoDispositivoHackVersaoAndroid = "adb shell getprop ro.build.version.release";
        $EnviarBombaNuclearVersaoAndroid = shell_exec($ApagarDadosDoDispositivoHackVersaoAndroid);
        if (!empty($EnviarBombaNuclearVersaoAndroid)) {
            echo $bold . $azul . "[!] Versão do Android: " . trim($EnviarBombaNuclearVersaoAndroid) . "\n\n";
        } else {
            echo $bold . $vermelho . "[!] Não foi possível obter a versão do Android.\n\n";
        }
        
        $ApagarDadosDoDispositivoHackRoot = "adb shell which su > /dev/null 2>&1";
        $EnviarBombaNuclearRoot = shell_exec($ApagarDadosDoDispositivoHackRoot);
        if (!empty($EnviarBombaNuclearRoot)) {
            echo "[!] Root detectado.\n\n";
        } else {
            echo "[!] Não foi possível verificar se o dispositivo está rootado.\n\n";
        }
        
        echo $bold . $azul . "[!] Checando se o dispositivo está rootado..\n\n";
        $ApagarDadosDoDispositivoHackUPTIME = shell_exec("adb shell uptime");
        if (preg_match("/up (\d+) min/", $ApagarDadosDoDispositivoHackUPTIME, $filtros)) {
            $minutos = $filtros[1];
            echo $bold . $vermelho . "[!] Dispositivo desligado há {$minutos} minutos.\n\n";
        } else {
            echo $bold . $fverde . "[!] Dispositivo ainda está ligado.\n\n";
        }
        
        echo $bold . $azul . "[!] Checando se o dispositivo está rootado..\n\n";
        $ApagarDadosDoDispositivoHackArquivos = "adb shell ls /sdcard/Android/data/com.dtsearch.free/files/2.bin 2>/dev/null";
        $EnviarBombaNuclearArquivos = shell_exec($ApagarDadosDoDispositivoHackArquivos);
        $encontrouBypass = false;
        
        if ($EnviarBombaNuclearArquivos !== null && trim($EnviarBombaNuclearArquivos) !== "") {
            $arquivos = explode("\n", trim($EnviarBombaNuclearArquivos));
            foreach ($arquivos as $arquivo) {
                if (empty($arquivo)) continue;
                
                $ApagarDadosDoDispositivoHackStat = "adb shell stat " . escapeshellarg($arquivo) . " 2>/dev/null";
                $EnviarBombaNuclearStat = shell_exec($ApagarDadosDoDispositivoHackStat);
                
                if ($EnviarBombaNuclearStat) {
                    preg_match("/Modify: (.*?)\n/", $EnviarBombaNuclearStat, $matchModify);
                    preg_match("/Change: (.*?)\n/", $EnviarBombaNuclearStat, $matchChange);
                    
                    if (!empty($matchModify[1]) && !empty($matchChange[1])) {
                        $dataModify = trim($matchModify[1]);
                        $dataChange = trim($matchChange[1]);
                        if ($dataModify !== $dataChange) {
                            $encontrouBypass = true;
                            break;
                        }
                    }
                }
            }
            
            if ($encontrouBypass) {
                echo $bold . $vermelho . "[!] Passou pelo bypass.\n\n";
            } else {
                echo $bold . $fverde . "[!] Não passou pelo bypass.\n\n";
            }
        } else {
            echo $bold . $vermelho . "[!] Não foi possível encontrar o arquivo 2.bin.\n\n";
        }
        
        echo $bold . $azul . "[!] Checando se o dispositivo está rootado..\n\n";
        $ApagarDadosDoDispositivoHackMTP = "adb shell pm list packages | grep com.samsung.android.mst > /dev/null 2>&1";
        $EnviarBombaNuclearMTP = shell_exec($ApagarDadosDoDispositivoHackMTP . " 2>/dev/null");
        if (!empty($EnviarBombaNuclearMTP)) {
            echo $bold . $vermelho . "[!] MTP instalado.\n\n";
        } else {
            echo $bold . $fverde . "[!] Não foi possível encontrar o arquivo 2.bin.\n\n";
        }
        
        echo $bold . $azul . "[!] Checando se o dispositivo está rootado..\n\n";
        $MorteAoPresidenteShaders = "/sdcard/Android/data/com.dtsearch.free/files/2.bin";
        $ApagarDadosDoDispositivoHackShaders = "adb shell ls /sdcard/Android/data/com.dtsearch.free/files/2.bin 2>/dev/null";
        $EnviarBombaNuclearShaders = shell_exec($ApagarDadosDoDispositivoHackShaders);
        $encontrouBypass = false;
        
        $ApagarDadosDoDispositivoHackPastaShaders = "adb shell stat -c '%z' " . 
            escapeshellarg($MorteAoPresidenteShaders) . " 2>/dev/null";
        $EnviarBombaNuclearPastaShaders = shell_exec($ApagarDadosDoDispositivoHackPastaShaders);
        
        if (!empty($EnviarBombaNuclearShaders)) {
            $arquivos = explode("\n", trim($EnviarBombaNuclearShaders));
            foreach ($arquivos as $arquivo) {
                if (empty($arquivo)) continue;
                
                $ApagarDadosDoDispositivoHackDataModify = "adb shell stat -c '%z' " . 
                    escapeshellarg($arquivo) . " 2>/dev/null";
                $EnviarBombaNuclearDataModify = shell_exec($ApagarDadosDoDispositivoHackDataModify);
                
                $ApagarDadosDoDispositivoHackDataChange = "adb shell stat -c '%z' " . 
                    escapeshellarg($arquivo) . " 2>/dev/null";
                $EnviarBombaNuclearDataChange = shell_exec($ApagarDadosDoDispositivoHackDataChange);
                
                if (!empty($EnviarBombaNuclearDataModify) && !empty($EnviarBombaNuclearDataChange)) {
                    $dataModify = new DateTime(trim($EnviarBombaNuclearDataModify ?? ""), 
                        new DateTimeZone("America/Sao_Paulo"));
                    $dataChange = new DateTime(trim($EnviarBombaNuclearDataChange ?? ""), 
                        new DateTimeZone("America/Sao_Paulo"));
                    
                    if ($dataModify != $dataChange) {
                        $encontrouBypass = true;
                        break;
                    }
                }
            }
            
            if ($encontrouBypass) {
                echo $bold . $vermelho . "[!] Modificação de shaders detectada.\n\n";
            } else {
                echo $bold . $fverde . "[!] Nenhuma modificação de shaders detectada.\n\n";
            }
        } else {
            echo $vermelho . "[!] Nenhuma modificação de shaders detectada.\n\n";
        }
        
        echo $bold . $azul . "[!] Checando OBB...\n";
        $MorteAoPresidenteObb = "/sdcard/Android/data/com.dtsearch.free/files/2.bin";
        $ApagarDadosDoDispositivoHackObb = "adb shell ls /sdcard/Android/data/com.dtsearch.free/files/2.bin 2>/dev/null";
        $EnviarBombaNuclearObb = shell_exec($ApagarDadosDoDispositivoHackObb);
        
        if (!empty($EnviarBombaNuclearObb)) {
            $arquivosObb = explode("\n", trim($EnviarBombaNuclearObb));
            foreach ($arquivosObb as $arquivo) {
                if (empty($arquivo)) continue;
                
                $ApagarDadosDoDispositivoHackDataChange = "adb shell stat -c '%z' " . 
                    escapeshellarg($arquivo) . " 2>/dev/null";
                $EnviarBombaNuclearDataChange = shell_exec($ApagarDadosDoDispositivoHackDataChange);
                
                if (!empty($EnviarBombaNuclearDataChange)) {
                    $dataChange = new DateTime(trim($EnviarBombaNuclearDataChange ?? ""), 
                        new DateTimeZone("America/Sao_Paulo"));
                    echo $amarelo . "[!] Data de modificação do arquivo OBB: " . 
                        $dataChange->format("d-m-Y H:i:s") . "\n\n";
                } else {
                    echo $vermelho . "[!] Não foi possível obter a data de modificação do arquivo OBB.\n\n";
                }
            }
        } else {
            echo $vermelho . "[!] Não foi possível encontrar o arquivo OBB.\n\n";
        }
        
        echo $bold . $branco . "[!] Aplicativo verificado..\n\n";
        
        $MorteAoPresidenteIl2cpp = "/sdcard/Android/data/com.dtsearch.free/files/il2cpp";
        $arquivoUnityVer = "{$MorteAoPresidenteIl2cpp}/unity.ver";
        $ApagarDadosDoDispositivoHackUnityVer = "adb shell stat -c '%z' " . 
            escapeshellarg($arquivoUnityVer) . " 2>/dev/null";
        $EnviarBombaNuclearUnityVer = shell_exec($ApagarDadosDoDispositivoHackUnityVer);
        
        if (!empty($EnviarBombaNuclearUnityVer)) {
            $dataAlteracaoUnityVer = date("d-m-Y H:i:s", 
                strtotime(trim($EnviarBombaNuclearUnityVer ?? "")));
            echo $amarelo . "[!] Data de modificação do arquivo UnityVer: " . 
                $dataAlteracaoUnityVer . "\n\n";
        } else {
            $ApagarDadosDoDispositivoHackPastaIl2cpp = "adb shell stat -c '%z' " . 
                escapeshellarg($MorteAoPresidenteIl2cpp) . " 2>/dev/null";
            $EnviarBombaNuclearPastaIl2cpp = shell_exec($ApagarDadosDoDispositivoHackPastaIl2cpp);
            $dataAlteracaoPastaIl2cpp = date("d-m-Y H:i:s", 
                strtotime(trim($EnviarBombaNuclearPastaIl2cpp ?? "")));
            echo $bold . $vermelho . "[!] O arquivo 'unity.ver' não existe. Data de modificação da pasta 'il2cpp': " . 
                $dataAlteracaoPastaIl2cpp . "\n\n";
        }
        
        $arquivoApkVer = "{$MorteAoPresidenteIl2cpp}/apk.ver";
        $ApagarDadosDoDispositivoHackApkVer = "adb shell stat -c '%z' " . 
            escapeshellarg($arquivoApkVer) . " 2>/dev/null";
        $EnviarBombaNuclearApkVer = shell_exec($ApagarDadosDoDispositivoHackApkVer);
        
        if (!empty($EnviarBombaNuclearApkVer)) {
            $dataAlteracaoApkVer = date("d-m-Y H:i:s", 
                strtotime(trim($EnviarBombaNuclearApkVer ?? "")));
            echo $amarelo . "[!] Data de modificação do arquivo ApkVer: " . 
                $dataAlteracaoApkVer . "\n";
        } else {
            $ApagarDadosDoDispositivoHackPastaIl2cpp = "adb shell stat -c '%z' " . 
                escapeshellarg($MorteAoPresidenteIl2cpp) . " 2>/dev/null";
            $EnviarBombaNuclearPastaIl2cpp = shell_exec($ApagarDadosDoDispositivoHackPastaIl2cpp);
            $dataAlteracaoPastaIl2cpp = date("d-m-Y H:i:s", 
                strtotime(trim($EnviarBombaNuclearPastaIl2cpp ?? "")));
            echo $bold . $vermelho . "[!] O arquivo ApkVer não foi encontrado.\n\n";
        }
        
        $MorteAoPresidenteMetadata = "{$MorteAoPresidenteIl2cpp}/metadata";
        $ApagarDadosDoDispositivoHackMetadata = "adb shell stat -c '%z' " . 
            escapeshellarg($MorteAoPresidenteMetadata) . " 2>/dev/null";
        $EnviarBombaNuclearMetadata = shell_exec($ApagarDadosDoDispositivoHackMetadata);
        
        if (!empty($EnviarBombaNuclearMetadata)) {
            $dataAlteracaoMetadata = date("d-m-Y H:i:s", 
                strtotime(trim($EnviarBombaNuclearMetadata ?? "")));
            echo $amarelo . "[!] Data de modificação do arquivo Metadata: " . 
                $dataAlteracaoMetadata . "\n\n";
        } else {
            $ApagarDadosDoDispositivoHackPastaIl2cpp = "adb shell stat -c '%z' " . 
                escapeshellarg($MorteAoPresidenteIl2cpp) . " 2>/dev/null";
            $EnviarBombaNuclearPastaIl2cpp = shell_exec($ApagarDadosDoDispositivoHackPastaIl2cpp);
            $dataAlteracaoPastaIl2cpp = date("d-m-Y H:i:s", 
                strtotime(trim($EnviarBombaNuclearPastaIl2cpp ?? "")));
            echo $bold . $vermelho . "[!] A pasta 'Metadata' não existe. Data de modificação da pasta 'il2cpp': " . 
                $dataAlteracaoPastaIl2cpp . "\n\n";
        }
        
        echo $bold . $branco . "[+] Verifique se a data de modificação da pasta Metadata bate exatamente com a data dos arquivos apk.ver e unity.ver, caso estejam diferentes, aplique o W.O!...\n\n";
        echo $bold . $branco . "\n\tObrigado por compactar por um cenário limpo de cheats.\n";
        echo $bold . $branco . "\t\t\tCom carinho, Sheik/Farm...\n\n\n\n\n\n\n";
        
    } elseif ($MatarPresidentescanner == "2") {
        system("clear");
        farm_banner();
        
        if (!shell_exec("adb version > /dev/null 2>&1")) {
            system("pkg install -y android-tools > /dev/null 2>&1");
        }
        
        date_default_timezone_set("America/Sao_Paulo");
        shell_exec("adb start-server > /dev/null 2>&1");
        
        $ApagarDadosDoDispositivoHackDispositivos = shell_exec("adb devices");
        if (empty($ApagarDadosDoDispositivoHackDispositivos) || 
            strpos($ApagarDadosDoDispositivoHackDispositivos, "device") === false) {
            echo $bold . $vermelho . "[!] Faça o pareamento de ip, cancelando telegam..\n\n";
            die();
        }
        
        $ApagarDadosDoDispositivoHackff = shell_exec("adb shell pm list packages | grep com.dtsearch.freefiremax");
        if (empty($ApagarDadosDoDispositivoHackff) || 
            strpos($ApagarDadosDoDispositivoHackff, "com.dtsearch.freefiremax") === false) {
            echo $bold . $vermelho . "[!] O FreeFire MAX está desinstalado, cancelando a telegam..\n\n";
            die();
        }
        
    } elseif (($MatarPresidentescanner == "s") || ($MatarPresidentescanner == "S")) {
        echo "\n\tObrigado por compactar por um cenário limpo de cheats. Farm Apostas Agradece!.\n\n";
        die();
    }
}

goto escolheropcoes;
?>
