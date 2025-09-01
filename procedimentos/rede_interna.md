<p align="center">
    <a href="../README.md">
        <img src="../imagens/aeph-logo.png" width="200px">
    </a>
</p>

<p align="center">
<b>Este projeto visa auxiliar o analista nas atividades relacionadas a Rede Interna da AEPH do Brasil.</b>
</p>
<!-- Comentário exemplo -->

<h1 id="conteudo" style="font-size:35px;">📝 Conteúdo</h1>

<!-- - <p style="font-size:20px"> <a href="#criartronco"> Criação de Tronco: Asterisk</a></p> -->
- <p style="font-size:20px"> <a href="#aduser"> AD: Criação de Usuário</a></p>
- <p style="font-size:20px"> <a href="#adgroup"> AD: Criação de Grupo</a></p>
- <p style="font-size:20px"> <a href="#pastarede"> Compartilhamento de Pasta</a></p>

<br>

<h1 id="aduser">🖥️ AD: Criação de Usuário</h1>

1. <p>Acessando o AD, vá em <b style="color:white; background-color:black">Usuários e Computadores do Active Driectory</b>. Nesta tela de administração de usuários, grupos e computadores do AD, clique na seguinte ordem, para listar os usuários:

        1 - aeph.com.br
        2 - AEPH
        3 - Usuários

No quadrante de número 4, está a listagem de usuários do AD.

</p>

<img src="../imagens/procedimentos-img/ad_usuario1.png" alt="AD Usuario1">

<br>

2. <p>Então, para criar um novo usuário, clique com o botão direito do mouse e vá em Novo Usuário.

</p>

<img src="../imagens/procedimentos-img/ad_usuario2.png" alt="AD Usuario2">

<br>

3. <p>Preencha as informações de acordo e não se esqueça de clicar em avançar.

</p>

<img src="../imagens/procedimentos-img/ad_usuario3.png" alt="AD Usuario3">

<br>

4. <p>Nesta dela, será definida a senha e configurações adicionais sobre a conta, então preencha de acordo com a necessidade. Para finalizar a criação de usuário, revise as informações e clique em Concluir.

</p>

<img src="../imagens/procedimentos-img/ad_usuario4.png" alt="AD Usuario4">


<img src="../imagens/procedimentos-img/ad_usuario5.png" alt="AD Usuario5">
<br>

5. <p> Para alterar a senha, adicionar o usuário a um grupo, desativar conta, excluir usuário ou ver as propriedades do mesmo, basta clicar com o botão direito em cima do mesmo.

</p>

<img src="../imagens/procedimentos-img/ad_usuario7.png" alt="AD Usuario7">


<br>


<h1 id="adgroup">🖥️ AD: Criação de Grupo</h1>

1. <p>Em <b style="color:white; background-color:black">Usuários e Computadores do Active Driectory</b>. Siga o seguinte caminho, para listar os grupos:

	1 - aeph.com.br
        2 - AEPH
        3 - Grupos

No quadrante de número 4, está a listagem de grupos do AD.

</p>

<img src="../imagens/procedimentos-img/ad_grupo1.png" alt="AD grupo1">

<br>

2. <p>Então, para criar um novo grupo, clique com o botão direito do mouse e vá em Novo Grupo.

</p>

<img src="../imagens/procedimentos-img/ad_grupo2.png" alt="AD grupo2">

<br>

3. <p>Preencha as informações de acordo e não se esqueça de clicar em Ok.

</p>

<img src="../imagens/procedimentos-img/ad_grupo3.png" alt="AD grupo3">

<br>

4. <p> Para adicionar um usuário a um grupo, excluir grupo ou ver as propriedades do mesmo, basta clicar com o botão direito em cima do mesmo. Então, para adicionar um novo usuário ao grupo, vamos clicar em Propriedades.

</p>

<img src="../imagens/procedimentos-img/ad_grupo4.png" alt="AD grupo4">


<br>

5. <p> Em propriedades, faça o seguinte passo a passo:

        1 - Membros
        2 - Adicionar
        3 - Digite o usuário/host
        4 - Clique em Verificar nomes
        5 - Ok
        6 - Ok

</p>

<img src="../imagens/procedimentos-img/ad_grupo6.png" alt="AD grupo6">

<br>


<h1 id="pastarede">🖥️ Compartilhamento de Pasta</h1>

1. <p>Para compartilhar uma pasta na rede, devemos fazer o seguinte procedimento:

Clique com o botão direito do mouse na pasta que deverá ser compartilhada, após clique em propriedades.


</p>

<img src="../imagens/procedimentos-img/pasta1.png" alt="pasta1">

<br>

2. <p>Em propriedades. siga o passo a passo abaixo:

        🔴
        1 - Compartilhamento.
        2 - Compartilhamento Avançado
        🟢
        3 - Marque Compartilhar a Pasta
        4 - Nomeie o Compartilhamento
        5 - Clique em Permissões
        🟣
        6 - Adicionar/Remover
        7 - Coloque o usuário ou grupo
        8 - Defina as Permissões
        9 - Aplicar e Ok

Essa etapa é fundamental, pois iremos definir quem poderá percorrer a pasta. Então, caso um usuário ou grupo não esteja na relação, não poderá nem acessar a pasta. No próximo passo, vamos definir a segurança da pasta. Portanto, vamos definir se o usuário/grupo terá alguma permissão especial, por exemplo, apenas leitura.
</p>

<img src="../imagens/procedimentos-img/pasta2.png" alt="pasta2">

<br>

3. <p> Na aba <b style="color:white; background-color:black">Segurança</b>, clique em Avançadas para ter uma visão ampla das configurações:

Agora na Tela de Configurações de Segurança Avançadas da Pasta, devemos mexer na aba de <b style="color:white; background-color:black">Permissões</b>. Nela podemos visualizar todos usuários/grupos e suas configurações de acesso, além de habilitar ou desativar herança.

Neste exemplo, vamos desabilitar a herança e permitir que o usuário emanoel.oliveira tenha Controle total apenas a pasta Teste, conforme imagem abaixo:
</p>

<img src="../imagens/procedimentos-img/pasta3.png" alt="pasta3">

<br>

4. <p> Agora dentro da pasta Teste, vamos negar o acesso do usuário emanoel.oliveira para a pasta <b style="color:white; background-color:black">Teste2</b>, então nas configurações de segurança, vamos adicionar uma Negação Total ao usuário, conforme imagem abaixo, atente-se que a herança deve estar desabilitada, pois caso esteja ativa o usuário poderá receber outra configuração proveniente da pasta raiz.
</p>

<img src="../imagens/procedimentos-img/pasta4.png" alt="pasta4">

<br>

5. <p> Com as configurações de acesso realizada, podemos notar que o usuário em questão consegue acessar sem problemas a pasta Teste, porém o mesmo não tem permissão para acessar a pasta Teste2.

</p>

<img src="../imagens/procedimentos-img/pasta5.png" alt="pasta5">

<br>

- <p style="font-size:20px"> <a href="#"> Voltar ao Topo</a></p>

<br>

- <p style="font-size:20px"> <a href="../README.md"> Voltar para a página principal</a></p>