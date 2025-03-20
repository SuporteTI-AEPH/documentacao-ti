<p align="center">
    <img src="../imagens/aeph-logo.png" width="200px">
</p>

<p align="center">
<b>Este projeto visa auxiliar o analista nas atividades relacionadas a telefonia da AEPH do Brasil.</b>
</p>

<!-- Comentário exemplo -->

<h1 id="conteudo" style="font-size:35px;">📝 Conteúdo</h1>

<!-- - <p style="font-size:20px"> <a href="#criartronco"> Criação de Tronco: Asterisk</a></p> -->
- <p style="font-size:20px"> <a href="#acessopabx"> Acesso ao PABX: Asterisk</a></p>
- <p style="font-size:20px"> <a href="#criarramal"> Criação Ramal e Inserção no Grupo: Asterisk</a></p>
- <p style="font-size:20px"> <a href="#VoIPs"> Configuração VoIPs</a></p>
- <p style="font-size:20px"> <a href="#rebootasterisk"> Reboot: Asterisk (Resolução de Problemas)</a></p>


<h1 id="acessopabx">🖥 Acesso ao PABX: Asterisk</h1>

1. <p>Para acessar o PABX, basta ir no cmd (ou qualquer ferramenta de linha de comando) e logar no <b>10.0.0.31</b> com o usuário root, neste caso do cmd do windows, utilizamos: <b style="color:white; background-color:black">ssh root@10.0.0.31</b>. A senha está armazenada no keepass.
</p>

<img src="../imagens/procedimentos-img/acesso_pabx1.png" alt="Acesso PABX1">

<br>


<h1 id="criarramal">🖥 Criação Ramal e Inserção no Grupo: Asterisk</h1>

1. <p>Dentro do PABX, vá até a pasta de configuração do Asterisk com o comando: <b style="color:white; background-color:black">cd /etc/asterisk</b>, após rode o comando: <b style="color:white; background-color:black">nano sip.conf</b> para editarmos o arquivo de configuração de Tronco/Ramais. (É possível também alterar o arquivo com o editor <b>VIM</b>)
</p>

<img src="../imagens/procedimentos-img/criar_userramal1.png" alt="Criar ramal1">

<br>



2. <p>No arquivo de configuração, adicione um novo ramal seguindo a configuração abaixo: 
<i>

	[NumeroRamal]
	type=friend
	username=NumeroRamal
	secret=NumeroRamal
	disallow=all
	allow=g729,alaw,ulaw
	context=ramais_11
	host=dynamic
	dtmfmode=rfc2833
	canreinvite=yes
	nat=yes                                   
	qualify=yes
	callgroup=1
	pickupgroup=1
	call-limit=3
	accountcode=NumeroRamal

</i> Lembre-se de seguir a concatenação
</p>

<img src="../imagens/procedimentos-img/criar_userramal2.png" alt="Criar ramal2">

<br>

<p>Com o novo ramal inserido, devemos salvar as alterações no arquivo com: <b style="color:white; background-color:black">CTRL X: S: CTRL X ou apenas CTRL O: CTRL X</b>.
</p>

3. <p>Agora devemos mexer no arquivo <b>queues.conf</b> para inserir o novo ramal em um grupo. Para isso, rode o comando abaixo:
    
<i>
	<b>nano queues.conf ou vi queues.conf </b>
</i>

</p>


4. <p>Dentro do arquivo, podemos notar que todos os grupos de ramais da AEPH  estão localizados dentro deles. Então, localize o grupo que deseja inserir o ramal novo. Neste exemplo, vamos utilizar o grupo de ramais da ITO, então para fácil localização de grupos. Dê <b style="color:white; background-color:black">CTRL W e busque por 2089, por exemplo</b>. No grupo adicione o novo ramal e finalize com: <b style="color:white; background-color:black">CTRL X: S: CTRL X ou apenas CTRL O: CTRL X</b>.

</p>

<img src="../imagens/procedimentos-img/add_ramalgp1.png" alt="Criar ramal4">


<!-- 
<i>
	<b>service asterisk reload ou sudo asterisk -rx</b>
</i>
-->

<br>

<h1 id="VoIPs">☎️ Configuração de VoIP</h1>

1. <p>No telefone, clique em MENU e procure por <b>STATUS</b>, dê <b>ENTER</b> e mais uma vez em <b>NETWORK STATUS</b>. Agora desça pelas informações até localizar o IP que o telefone recebeu e guarde essa informação, pois vamos precisar dela para realizar a configuração do ramal.
</p>

<img src="../imagens/procedimentos-img/config_tel0.jpeg" alt="configuração voip0">

<br>

2. <p>No navegador, coloque o IP obtido e preencha o campo de login com os dados armazenados no Keepass.
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

<h1 id="rebootasterisk">🖥 Reboot: Asterisk (Resolução de Problemas)</h1>

1. <p>Caso o PABX (Asterisk), começe a apresentar problemas de ligações ou a URA em inglês, devemos realizar o procedimento de reboot do serviço. Logado no servidor, rode o comando <b><i>rasterisk</i></b>, note que no exemplo abaixo, há dois erros de TIMEOUT de registro do servidor localizado na GTGI. Mas, pode ser que não seja retornado nenhuma mensagem de erro.
</p>

<img src="../imagens/procedimentos-img/reboot_asterisk1.png" alt="reboot PABX1">

<br>

2. <p>Rodando o comando, <b><i>sip show registry</i></b>, podemos notar também o erro de registro relatado no passo anterior.
</p>

<img src="../imagens/procedimentos-img/reboot_asterisk2.png" alt="reboot PABX2">

<br>

3. <p>Agora devemos parar o serviço do asterisk, então rode <b><i>core stop now</i></b>, para desabilitar o serviço de telefonia.
</p>

<img src="../imagens/procedimentos-img/reboot_asterisk3.png" alt="reboot PABX3">

<br>

4. <p><i>(OPCIONAL)</i> Para termos certeza que todas conexões do asterisk, foram encerradas, podemos derrubar todas conexões via Mikrotik.<b><i> 
ATENÇÃO, O PROCEDIMENTO IRÁ DERRUBAR A CONEXÃO DE INTERNET DA AEPH POR ALGUNS INSTANTES, ENTÃO REALIZE ESSE PASSO QUANDO FOR TOTALMENTE NECESSÁRIO E COM PERMISSÃO DE SEU SUPERIOR</i></b>. 

Já logado no mikrotik, vá em <b style="color:white; background-color:black">IP: Firewall: Connections</b>, então dê um <b style="color:white; background-color:black">CTRL A</b> para selecionar todos os STATES e clique no sinal de <b style="color:white; background-color:black">- (podendo ser <i>Remove</i>, dependendo da versão que está utilizando)</b>, repita esse processo duas vezes!
</p>

<img src="../imagens/procedimentos-img/reboot_asterisk4.png" alt="reboot PABX4">

<br>

5. <p>Com o Asterisk parado, vamos inicia-lo com o seguinte comando:

<i>

	service asterisk start
</i>

</p>

6. <p>Com o serviço iniciado, volte para o PABX, entrando novamente na linha de comando do asterisk com o <b><i>rasterisk</i></b> e dê o <b><i>sip show registry</i></b>, assim já será possível identificar ambos hosts registrados e em funcionamento. Caso preferir, pode ficar nesta tela e ver os logs de ligações subindo.
</p>

<img src="../imagens/procedimentos-img/reboot_asterisk5.png" alt="reboot PABX5">

<br>

- <p style="font-size:20px"> <a href="#"> Voltar ao Topo</a></p>

<br>

- <p style="font-size:20px"> <a href="../README.md"> Voltar para a página principal</a></p>