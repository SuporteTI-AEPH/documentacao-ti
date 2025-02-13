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


<h1 id="winbox">📧 Winbox e o acesso ao Mikrotik</h1>

1. <p>Acesse o <a href="https://mikrotik.com/download">Link de Download</a> do <b style="color:white; background-color:black">Winbox</b> e baixe a versão do software de acordo com o seu sistema operacional. 
</p>


<img src="../imagens/procedimentos-img/winbox_1.png" alt="Winbox Download1">

<br>

2. <p>Com o download efetuado, coloque o arquivo <b style="color:white; background-color:black">WinBox_Windows.zip</b> onde desejar e realize o processo de unzip. Note que será gerado o aplicativo <b style="color:white; background-color:black">Winbox</b> e já estará disponível para uso. 
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

<h1 id="criarrede">📧 Criação de Interface e Rede</h1>

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

<h2 id="criarredelan"> Criação de DHCP para LAN</h2>

<br>

1. <p> Para criar um servidor de DHCP para a rede local, vá em <b style="color:white; background-color:black">IP: DHCP Server: Networks</b>, preecnha as informações com os dados que tiver, após finalize com <b style="color:white; background-color:black">Apply, Ok.</b>
</p>


<img src="../imagens/procedimentos-img/interface-criacao7.png" alt="Cria rede lan 1">

<br>

1. <p> Ainda em DHCP Server, vá em <b style="color:white; background-color:black">DHCP: New</b>, preecnha as informações com o <b style="color:black; background-color:white">nome da Rede, InterfaceCriada, TempoDeLease, RangedeIPs (criado no passo anterior)</b> e por fim, marque a opção: <b style="color:black; background-color:white">Add ARP For Leases</b>, finalizando com, <b style="color:white; background-color:black">Apply e Ok.</b>
</p>


<img src="../imagens/procedimentos-img/interface-criacao8.png" alt="Cria rede lan 2">

<br>

<div>

[BADGE1]: https://img.shields.io/badge/Página_principal-000?style=for-the-badge&logo=html



<!-- <h1 id="voltar">Voltar para a página principal</h1>

[![backend-simple][BADGE1]](../README.md)-->


</div>


<br>

- <p style="font-size:20px"> <a href="#"> Voltar ao Topo</a></p>

<br>

- <p style="font-size:20px"> <a href="../README.md"> Voltar para a página principal</a></p>