

GA-lite
---

Ao inserir o Google Analytics no website, não é possível conseguir uma pontuação 100/100 no Pagespeed do Google.

Há 3 soluções viáveis para este problema:


# 1. Inserir biblioteca [GA-lite](https://github.com/jehna/ga-lite) (recomendado)        

Insira o seguinte código antes do fechamento da tag ´<body>´:            
    
        <script src="https://cdn.jsdelivr.net/ga-lite/latest/ga-lite.min.js" async></script>
        <script>
            var galite = galite || {};
            galite.UA = 'UA-XXXXXX'; // Insert your tracking code here
        </script>



# 2. Armazenar o script do GA no servidor local e criar um *cron* diário (atualizar a biblioteca diarimente). Veja o tutorial no link:

    `http://diywpblog.com/leverage-browser-cache-optimize-google-analytics/`



# 3. O Google está te enganando, você pode enganá-lo de volta. Insira uma condicional para evitar servir o script de análise para PageSpeed:

        <?php if (!isset($_SERVER['HTTP_USER_AGENT']) || stripos($_SERVER['HTTP_USER_AGENT'], 'Speed Insights') === false): ?>
            // your analytics code here
        <?php endif; ?>

Ou em js...

        if(navigator.userAgent.indexOf("Speed Insights") == -1) {
            // your analytics code here
        }

