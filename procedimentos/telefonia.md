<p align="center">
    <img src="../imagens/aeph-logo.png" width="200px">
</p>

<p align="center">
<b>Este projeto visa auxiliar o analista nas atividades relacionadas a telefonia da AEPH do Brasil.</b>
</p>

<!-- Comentário exemplo -->

<h1 id="conteudo" style="font-size:35px;">📝 Conteúdo</h1>

- <p style="font-size:20px"> <a href="#VoIPs"> Configuração VoIPs</a></p>


<h1 id="VoIPs">☎️ Configuração de VoIP</h1>

1. <p>No telefone, clique em MENU e procure por STATUS, dê ENTER e novamente em NETWORK STATUS. Procure pelo IP que o telefone recebeu, pois vamos precisar dessa informação para fazer a configuração do ramal.
</p>

<br>

2. <p>No navegador, coloque o IP obtido e preencha o campo de login com os dados presentes no Keepass.
</p>

<img src="../imagens/procedimentos-img/config_tel1.png" alt="configuração voip1">


<br>

3. <p>Já dentro do VoIP, vá na aba <b style="color:white; background-color:black">Configuration: Quick Setup</b> e preencha cada aba com as seguintes informações:
- LAN SETUP:
- - Caso preferir deixar como DHCP, não será necessário alterar a configuração. Porém, se for IP estático, coloque as informações de rede de acordo com a rede da AEPH.
- SIP Proxy and Register
- - Enable, IPservidorPABX (10.0.0.31), porta (5060), Disable, Enable, IPservidorPABX  (10.0.0.31), porta (5060).
- Line Settings
- - 1, Enable, NomeDisplayDeLigação, NúmeroRamal, UsuárioAutenticaçãoDoPABX, SenhaDeUsuárioPABX (por padrão o mesmo que o nome de usuário).

Após realizar as configurações, basta clicar em <b style="color:white; background-color:black">Submit</b>, no canto inferior direito da tela e validar a efetuação e recebimentos de ligações..
</p>

<img src="../imagens/procedimentos-img/config_tel2.png" alt="configuração voip2">
<img src="../imagens/procedimentos-img/config_tel3.png" alt="configuração voip3">

<br>

- <p style="font-size:20px"> <a href="#"> Voltar ao Topo</a></p>

<br>

- <p style="font-size:20px"> <a href="../README.md"> Voltar para a página principal</a></p>