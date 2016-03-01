title: Configurando Filtros para Contact Form 7
thumbnail: gallery/img-configurando-contact-form-7-hooks.png
banner: gallery/img-configurando-contact-form-7-hooks.png
category:
  - Wordpress
tags:
  - wordpress
  - contact-form-7
  - wp-hooks
categories:
  - Wordpress
date: 2015-10-06 15:43:00
---

## Introdução
O [Contact Form 7](http://contactform7.com) é um plugin para criação de Formulário de Contato para **Wordpress** presente em mais de um milhão de websites e com mais de 30 milhões de downloads. Sem dúvida, seu sucesso se deve à sua simplicidade e eficácia.

## Vantagens do Contact Form 7
Embora seja simples, ele oferece algumas opções de customização, como a criação facilitada do formulário, formato do email enviado, tradução das mensagens e mais alguns detalhes expecíficos.

Sua arquitetura ainda permite a criação de plugins que adicione ou modifique funcionalidades, tornando-o ainda mais poderoso.

## Limitações do Contact Form 7
O ecossistema de plugins Wordpress que envolvem o Contact Form 7 é grande, porém ainda há casos em que precisamos de uma funcionalidade ainda não implementada.

Uma opção é modificarmos o código fonte do plugin, adicionando o que precisamos, mas isso não é uma boa prática, já que se tivermos que atualizar o plugin para uma versão mais recente, perderemos nossas modificações - ou teremos que fazer tudo novamente.

Resta-nos seguir as boas práticas de programação Wordpress: criar um plugin. Um plugin é interessante quando precisamos reutilizar suas funcionalidades. Porém criá-lo necessidade de alguns procedimentos que levam tempo e não justificam apenas um pequeno ajuste.

Caso precisemos de algo pontual, podemos utilizar uma estratégia mais simples: o mecanismo de [Hooks](http://codex.wordpress.org/Plugin_API/Hooks) do Wordpress, o mesmo utilizado por Plugins.

## Utilizando WP Hooks com Contact Form 7
Com algum conhecimento em PHP, já podemos trabalhar com os [*Actions*](http://codex.wordpress.org/Glossary#Action) e [*Filters*](http://codex.wordpress.org/Glossary#Filter). Para isso, precisamos checar se o plugin que queremos modificar suporta essa funcionalidade.

Se na documentação do plugin não tiver uma lista dos seus Hooks, teremos que procurar no código fonte. E isso é bem tranquilo. Basta buscarmos pelo código que criar o Hook: as funções ***do_action()*** e ***apply_filters()***

Se buscarmos no código fonte do plugin Contact Form 7 por essas funções, identificamos 72 resultados, sendo 25 actions e 47 filtros.

O nome das actions e filters é geralmente auto explicativo, mas é importante vermos no código fonte em que etapa ele é chamado e ver quais informações teremos disponíveis para manipulação

Para esse exemplo, utilizarei o filtro chamado "**wpcf7_mail_components**" que está na linha 57 do arquivo */contact-form-7/includes/mail.php*

``` php
$components = apply_filters( 'wpcf7_mail_components',
			$components, wpcf7_get_current_contact_form() );
```

**$components** é um Array que armazena os dados a serem enviados por email, desde o destinatário, remetente e o corpo do email. Vamos utilizar esse filtro para manipular o conteúdo do email e adicionar uma mensagem no final.

Observe a quantidade de argumentos enviados após o nome do filtro. Nesse caso, são enviados dois valores para a função hook: ***$components*** e ***wpcf7_get_current_contact_form()***, que podem ou não utilizados no hook. Vai depender da necessidade.

## Criando o Filtro para Manipulação do E-mail

Agora que identificamos o filtro que soluciona nosso problema, vamos seguir a sintaxe do Wordpress para acoplar uma função "hook".

``` php
/**
 * Primeiro parâmetro é o nome do filtro
 * Segundo parâmetro é o nome da função a ser chamada
 * Terceiro parâmetro é a prioridade, caso tenha mais de uma função nesse hook
 * Quarto parâmetro é a quantidade de argumentos enviados à função hook
 */
add_filter( 'wpcf7_mail_components', 'filter_append_msg_to_email', 10, 2);
```

E por fim, a criação da função hook, onde o mais importante acontece:

``` php
function filter_append_msg_to_email( $components, $form)
{
    $email_body = $components['body'];

    $msg_adicional = '<p>Linha adicionada através de um filtro!</p>';

    $email_body = $email_body . $msg_adicional;

    $components['body'] = $email_body;

    return $components;
}
```
Agora é só testar o envio do email e checar se a frase foi adicionada.

## Conclusão
Sem dúvida o Contact Form 7 é um ótimo plugin para criação de formulários de contato em Wordpress. Se suas funcionalidades padrão não forem suficientes, é possível instalar outros plugins para melhorá-lo.

Caso precise de alguma funcionalidade específica, utilize o mecanismo de Hooks do Wordpress para customizá-lo, sem alterar seu código fonte.

Os Hooks do Wordpress podem ser muito úteis se utilizados corretamente, e podem tornar o Contact Form 7 é muito mais poderoso!

E você? Diga-nos sua opinição sobre Contact Form 7 e como decidiram utilizá-lo!
