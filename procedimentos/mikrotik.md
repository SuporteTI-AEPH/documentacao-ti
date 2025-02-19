<p align="center">
    <img src="../imagens/aeph-logo.png" width="200px">
</p>

<p align="center">
<b>Este projeto visa auxiliar o analista nas atividades relacionadas ao Mikrotik da AEPH do Brasil.</b>
</p>

<!-- Comentário exemplo -->

<h1 id="conteudo" style="font-size:35px;">📝 Conteúdo</h1>

- <p style="font-size:20px"> <a href="#winbox">Winbox e o acesso ao Mikrotik</a></p>
- <p style="font-size:20px"> <a href="#criarrede"> Criação de Interface e Rede</a></p>
- -  <p style="font-size:15px"> <a href="#criarredelan"> Criação de DHCP para LAN</a></p>
- -  <p style="font-size:15px"> <a href="#craltpppoe"> Criar ou Alterar Configuração PPPoe</a></p>
- <p style="font-size:20px"> <a href="#regranatfw"> Criação de Regras: NAT e Firewall</a></p>
- -  <p style="font-size:15px"> <a href="#criarnat"> Criação de Regra: NAT</a></p>
- -  <p style="font-size:15px"> <a href="#criarfw"> Criação de Regra: Filter Rule (Firewall)</a></p>



<h1 id="winbox">🧱 Winbox e o acesso ao Mikrotik</h1>

1. <p>Acesse o <a href="https://mikrotik.com/download">Link de Download</a> do <b style="color:white; background-color:black">Winbox</b> e baixe a versão do software de acordo com o seu sistema operacional. 
</p>


<img src="../imagens/procedimentos-img/winbox_1.png" alt="Winbox Download1">

<br>

2. <p>Com o download efetuado, coloque o arquivo <b style="color:white; background-color:black">WinBox_Windows.zip</b> onde desejar e realize o processo de unzip. Note que será gerado o aplicativo <b style="color:white; background-color:black">Winbox</b> já disponível para uso. 
</p>


<img src="../imagens/procedimentos-img/winbox_2.png" alt="Winbox Download1">

<br>

3. <p>Com o Winbox aberto, já será mostrado o Mikrotik disponível para acesso. Então, para acessa-lo, <b style="color:white; background-color:black">selecione-o ou digite manualmente o endereço</b>. Após coloque o login e senha (disponíveis no keepass) e clique em conectar.
</p>


<img src="../imagens/procedimentos-img/winbox_3.png" alt="Winbox Download1">

<br>

- 3.1 Por padrão, pode ser que o firewall do Windows pergunte, se será liberado o acesso do Winbox a rede do domínio, para liberar o acesso, basta clicar em <b style="color:white; background-color:black">Permitir acesso</b> e seguir com o passo anterior.  
</p>


<img src="../imagens/procedimentos-img/winbox_3.1.png" alt="Winbox Download1">

<br>

<h1 id="criarrede">🧱 Criação de Interface e Rede</h1>

1. <p>Para criar o tipo de interface, vá em <b style="color:white; background-color:black">Interfaces: Interface: New</b> e selecione o tipo de interface que deseja criar, no caso será <b style="color:white; background-color:black">Ethernet</b>.
</p>


<img src="../imagens/procedimentos-img/interface-criacao1.png" alt="Cria rede1">

<br>

2. <p>Ainda em <b style="color:white; background-color:black">Interfaces</b> vá em <b style="color:white; background-color:black">Interface List: New</b> para criarmos uma nova interface. Neste caso, vamos nomea-la e selecionar o (tipo) interface criada no passo anterior e dê um <b style="color:white; background-color:black">Apply, Ok.</b>
</p>


<img src="../imagens/procedimentos-img/interface-criacao2.png" alt="Cria rede2">

<br>

3. <p>Agora vá em <b style="color:white; background-color:black">IP: Addresses: New</b> e preencha os campos com o <b style="color:black; background-color:white">Nome, IP designado+máscara de rede, IP de rede e a interface</b>. Após dê <b style="color:white; background-color:black">Apply, Ok.</b>
</p>


<img src="../imagens/procedimentos-img/interface-criacao3.png" alt="Cria rede3">

<br>

4. <p>Indo em <b style="color:white; background-color:black">IP: Routes: New</b> preencha os campos com o <b style="color:black; background-color:white">Nome, 0.0.0.0/0 (para definir qualquer destino) e gateway</b>. Após dê <b style="color:white; background-color:black">Apply, Ok.</b>
</p>


<img src="../imagens/procedimentos-img/interface-criacao4.png" alt="Cria rede4">

<br>

5. <p> Vá para <b style="color:white; background-color:black">IP: Firewall: NAT: New</b> para podermos criar um NAT se saída, com objetivo de mascarar o IP da rede.
</p>


<img src="../imagens/procedimentos-img/interface-criacao5.png" alt="Cria rede5">

<br>

6. <p> Com a aba aberta, preencha os campos com <b style="color:black; background-color:white">Nome Regra, srcnat, InterfaceCriada, Masquerade</b>, após finalize com <b style="color:white; background-color:black">Apply, Ok.</b>
</p>


<img src="../imagens/procedimentos-img/interface-criacao6.png" alt="Cria rede6">

<br>

<h2 id="criarredelan">🧱 Criação de DHCP para LAN</h2>

<br>

1. <p> Para criar um servidor de DHCP para a rede local, vá em <b style="color:white; background-color:black">IP: DHCP Server: Networks</b>, preencha as informações com os dados que tiver, após finalize com <b style="color:white; background-color:black">Apply, Ok.</b>
</p>


<img src="../imagens/procedimentos-img/interface-criacao7.png" alt="Cria rede lan 1">

<br>

1. <p> Ainda em DHCP Server, vá em <b style="color:white; background-color:black">DHCP: New</b>, preecnha as informações com o <b style="color:black; background-color:white">nome da Rede, InterfaceCriada, TempoDeLease, PoolDeDHCP (criado no passo anterior)</b> e por fim, marque a opção: <b style="color:black; background-color:white">Add ARP For Leases</b>, finalizando com, <b style="color:white; background-color:black">Apply e Ok.</b>
</p>


<img src="../imagens/procedimentos-img/interface-criacao8.png" alt="Cria rede lan 2">

<br>

<h2 id="craltpppoe">🧱 Criar ou Alterar Configuração PPPoe</h2>

<br>

1. <p> Para criar ou alterar uma conexão PPPoe, vá em <b style="color:white; background-color:black">PPP: INTERFACES</b>, sendo que para criar um novo, clique em <b style="color:white; background-color:black">New</b>, para alterar um já existente, dê duplo click no mesmo, assim preenchendo as informações passadas pela provedora de internet, terminando com <b style="color:white; background-color:black">Apply, Ok.</b>
</p>


<img src="../imagens/procedimentos-img/pppoe_alteracao1.png" alt="Cria e Altera Conexão PPPoe">

<br>

<h1 id="criarrede">🧱 Criação de Interface e Rede</h1>

1. <p>Para criar o tipo de interface, vá em <b style="color:white; background-color:black">Interfaces: Interface: New</b> e selecione o tipo de interface que deseja criar, no caso será <b style="color:white; background-color:black">Ethernet</b>.
</p>


<img src="../imagens/procedimentos-img/interface-criacao1.png" alt="Cria rede1">

<br>

<h1 id="regranatfw">🧱 Criação de Regras: NAT e Firewall</h1>

<h2 id="criarnat">🧱 Criação de Regra: NAT</h2>

1. <p>Para criar um NAT de tipo <b style="color:white; background-color:black"> SRCNAT</b>, vá em <b style="color:white; background-color:black">IP: Firewall: NAT: New</b>, expanda os campos de <b style="color:black; background-color:white">General e Action</b>, preenchendo com seguintes dados: <b style="color:white; background-color:black">NomeDaRegra, srcnat, Interface (Com WAN configurada), SRC-NAT e o IPdaInterface </b>, terminando com um <b style="color:white; background-color:black">Apply, OK</b>.
</p>


<img src="../imagens/procedimentos-img/criar_nat1.png" alt="Cria nat1">

<br>

2. <p>Para criar um NAT de tipo <b style="color:white; background-color:black"> MASQUERADE</b>, vá em <b style="color:white; background-color:black">IP: Firewall: NAT: New</b>, expanda os campos de <b style="color:black; background-color:white">General e Action</b>, utilize as seguintes informações: <b style="color:white; background-color:black">NomeDaRegra, srcnat, Interface (Com WAN configurada), Masquerade</b> e finalizando com <b style="color:white; background-color:black">Apply, OK</b>.
</p>


<img src="../imagens/procedimentos-img/criar_nat1.png" alt="Cria nat2">

<br>

3. <p>Agora, para criar um NAT de tipo <b style="color:white; background-color:black"> DSTNAT</b>, abra a mesma aba de criação de NAT, expandindo também os campos de <b style="color:black; background-color:white">General e Action</b>, preenchendo os campos sinalizados com: <b style="color:white; background-color:black">NomeDaRegra, dstnat, IPdeOrigem (de onde está vindo a requisição de acesso), Protocolo, PortaQueEstáChegandoARequisição, dst-nat, IPInterno (IP que irá receber o acesso)</b>. No último campo, se preferir pode definir uma porta que será redirecionado o acesso. E assim, finalizando com <b style="color:white; background-color:black">Apply, OK</b>.
</p>


<img src="../imagens/procedimentos-img/criar_nat3.png" alt="Cria nat3">

<br>

<h2 id="criarfw">🧱 Criação de Regra: Filter Rule (Firewall)</h2>

<br>

-  Para criação de regras de firewall, utilizamos três tipos de Chain:

- - Forward - para pacotes que passam pelo roteador;
- - Input - pacotes que entram pelo roteador passando por uma das interfaces, com IP de destino sendo um dos endereços do mikrotik;
- - Output - para pacote originados do roteador que vão sair por uma das interfaces. 

1. <p>Para criar uma regra, vá em <b style="color:white; background-color:black">IP: Firewall: Filter Rules: New</b> marque os campos, <b style="color:black; background-color:white">General: Action</b> e coloque: <b style="color:white; background-color:black"> NomeRegra, Chain, SrcAddress, Protocolo, SrcPort</b> e confirme que a ação está como <b style="color:white; background-color:black">Accept</b>, por fim, aplique e dê Ok.
- - Para criar a regra como objetivo de liberar o acesso externamente, basta utilizar a Chain como Output e utilizar os campos de Dst. Além disso, é possível também, utilizar listas de IPs ou as interfaces diretamente.
</p>


<img src="../imagens/procedimentos-img/criar_regra1.png" alt="Cria regra1">

<br>

- <p style="font-size:20px"> <a href="#"> Voltar ao Topo</a></p>

<br>

- <p style="font-size:20px"> <a href="../README.md"> Voltar para a página principal</a></p>