

# Utilização do pushstate

** Alterar estado da página sem dar refresh no navegador **



## Aplicação

Exemplo de utilização:

    History.pushState({state: 1}, "Title", "/to/url/");


Evento ao alterar estado:

    // Bind to State Change
    (function(window,undefined){
        History.Adapter.bind(window,'statechange',function(){ // Note: We are using statechange instead of popstate

            loadPage(location.href);

            // Log the State
            var State = History.getState(); // Note: We are using History.getState() instead of event.state
            History.log('statechange:', State.data, State.title, State.url);
        });

    })(window);


    loadPage = function(href) {
        $("#content").load(href+" #content>*");
    };



## History

Para garantir uma boa utilização (cross-browser) chame apenas a biblioteca ´Hitory.js´. Você pode baixar pelo [Github](https://github.com/browserstate/history.js/).

    


