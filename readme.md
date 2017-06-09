<p align="center"><img src="https://laravel.com/assets/img/components/logo-laravel.svg"></p>

<p align="center">
<a href="https://travis-ci.org/laravel/framework"><img src="https://travis-ci.org/laravel/framework.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://poser.pugx.org/laravel/framework/d/total.svg" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://poser.pugx.org/laravel/framework/v/stable.svg" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://poser.pugx.org/laravel/framework/license.svg" alt="License"></a>
</p>


## Configurações

Para Fazer a api funcionar é necessário:

- Clonar o projeto
- Rodar o composer install na pasta root do projeto
- Configurar o .env (para esta api foi utilizado o MySQL como SGBD)
- Rodar php artisan:migrate --seed. São duas migrations simples que servem apenas de exemplo e já tem alguns dados que serão inseridos com o --seed
- Rodar php artisan make:auth. Faz o sistema de login e registro de novos usuários funcionar.

Foram utilizados 2 pacotes:

- laravel/passport. https://laravel.com/docs/5.4/passport
- barryvdh/laravel-cors. https://github.com/barryvdh/laravel-cors

Para a configuração dos dois basta seguir as instruções dos links disponibilizados acima.

Depois de configurar tudo, crie um novo usuário no sistema e acesse a url http://localhost:8000/oauth/token via POST enviando os seguintes parametros:

- grant_type: password.
- client_id: id gerado pelo passport, geralmente ele gera 2 se um não estiver funcionando teste o outro.
- client_secret: tambem gerado pelo passport.
- username: email do usuario que voce criou.
- password: senha do usuario

Esta url vai te retornar um token, guarde-o pois é com ele que você vai conseguir fazer os requests para a API.

Para testar foi utilizado o Postman, é um pluggin do google chrome. https://chrome.google.com/webstore/detail/postman/fhbjgbiflinjbdggehcddcbncdddomop

As seguintes urls ficam disponíveis para teste:

- http://localhost:8000/api/banks
- http://localhost:8000/api/accounts
