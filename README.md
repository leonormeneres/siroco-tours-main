TODO:
- language switcher

- menu esta colado ao titulo em mobile
- links dos tours/artigos relacionados nao podem ter underline
- imagens nao estao optimizadas

------------------------------------------------------------
------------------------------------------------------------
------------------------------------------------------------

npx tinacms dev -c "hugo server -D -p 1313"

------------------------------------------------------------
------------------------------------------------------------
------------------------------------------------------------

FORM:
criar / editar:
https://dashboard.reform.app/forms

formHiddenFormId e dependente do idioma (config.toml), porque cada idioma tem um form separado e com um ID unico:

  <!-- Contact form -->
  <div id="my-reform"></div>
  <script>window.Reform = window.Reform || function () { (Reform.q = Reform.q || []).push(arguments) };</script>
  <script id="reform-script" async src="https://embed.reform.app/v1/embed.js"></script>
  <script>
    Reform('init', {
      url: 'https://forms.reform.app/TgS8EL/form-{{ $.Site.Language }}/k6elm2?{{ .Site.Params.formHiddenFormId }}={{ .Permalink | absURL }}',
      target: '#my-reform',
      background: 'default',
    })
  </script>

------------------------------------------------------------
------------------------------------------------------------
------------------------------------------------------------

Contact form estilizado (redireciona para o reform.app)

<form method="POST" action="https://forms.reform.app/headless/TgS8EL/form-pt/k6elm2/submissions">
    <br>
    <div class="article_title">Let's make it happen!</div>
    <div class="article_paragraph">
        <p>Send us your selected preferences so we can start designing your dream journey.</p>
        <br>
    </div>

    <div id="form">
        <input type="text" id="cc81c880-aab1-4d5f-ab8d-650620318447"
            name="answers[cc81c880-aab1-4d5f-ab8d-650620318447]" placeholder="Name" required />

        <input type="text" id="e2ec3e9b-04ce-4c4a-99f1-8b7180494c5b"
            name="answers[e2ec3e9b-04ce-4c4a-99f1-8b7180494c5b]" placeholder="Email" required />

        <input type="text" id="eb9c7406-78d6-46dd-8ef2-8049d4eeca80"
            name="answers[eb9c7406-78d6-46dd-8ef2-8049d4eeca80]" placeholder="Contacto telefónico" />

        <br>

        <textarea id="cda4930b-b3e7-4228-9c03-421c52be5c82" name="answers[cda4930b-b3e7-4228-9c03-421c52be5c82]"
            placeholder="A sua mensagem" required></textarea>

        <input type="hidden" id="f8dfebb0-c171-4182-9376-643434e4d241"
            name="answers[f8dfebb0-c171-4182-9376-643434e4d241]" />
        <div class="center"><input type="submit" value="send"></div>
        <div id="more">We will get back to you with a proposal</div>
</form>


------------------------------------------------------------
------------------------------------------------------------
------------------------------------------------------------





{{ $__flag_us := ($.Site.GetPage "section" "uploads").Resources.GetMatch "__flag_us.png" }}
src="{{ $__flag_us.RelPermalink }}"