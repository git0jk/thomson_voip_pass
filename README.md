# thomson_voip_pass
Retirar password voip de um router thomson, que usa configuração Dinamica (descarregada do operador (ISP) durante o arranque)

Boas a todos..

Infelizmente Portugal é um país ainda retrogado e mesquinha, feito de bebés chorões e outros coitadinhos,
e com toda a tendência para nivelar conhecimentos, sempre pelo mais burro. Tipo: "se o nivel de conhecimento
dos que me rodeiam for alto, depois eu já não sou bom. Prefiro que eles sejam burros para me destacar".

Esta é a mentalidade dos cromos que administram o 'forum.zwame.pt', no qual decidi perder um pouco de tempo a esclarecer algumas duvidas técnicas ao povo Tuga, e no dia seguinte foi tudo apagado. Foi das poucas vezes que postei algo publicamente e esmerei-me a escrever, com o intuito de esclarecer as duvidas de uma vez por todas; duvidas tecnicas, que quem trabalha em redes/servers tem direito a saber. Houve tempos em que eu tambem não sabia, e alguem se ergueu pra mim, por isso queria pagar na mesma moeda. Ninguem me crackou passwords (e eu tambem não o fiz a ninguem (nem sei lol)), mas mostraram o que devia aprender/pesquisar para um dia o conseguir. Foi optimo pra mim, porque atrás disso veio tudo o q sei hoje (que sinceramente, não é muito, mas..)

Então decidi criar este git para ir esclarecendo esta ou outras duvidas que eu possa|saiba ajudar. Não esperem respostas rápidas, mas vou tentar. 

######################################
No link seguinte podem ver o post já filtrado, onde a ultima resposta (post 106, que pode ser alterado a qualquer momento, claro) ficou novamente "Não consegues" (That doesn't empower you. But it's the real purpose):
https://forum.zwame.pt/threads/como-trocar-router-da-meo-fibra.720871/page-6
######################################
<br>
E aqui ficam as ultimas mensagens que apagaram do forum (conversa imcompleta). Eles dizem que apagaram os Posts pela maneira como me dirigi a outro membro, mas toda a gente desconfia do real motivo, certo? (Até porque não apagaram só este ultimo POST, mas tambem, os outros 2 ou 3 onde estavam outras maneiras de o fazer. Logo volto a escrevê-las. Por fim, quem vê o outro dizer "GARANTO-TE a 100%" ou "tenho a CERTEZA QUE FUNCIONA ASSIM", espero que conclúa que este b0rd4 m3rd4 anda no forum a dizer isto pra voces pensarem ser mesmo verdade, e nem sequer tentarem. "MIND GAMES". But you should always remember this:<br>
    "Never believe a prediction that doesn't empower you"                  <br>  ## Nunca acredites numa predição que não te fortifique. <br>
      https://www.youtube.com/watch?v=smjszXNTkoM
<br>

###################################################################
From: info@zwame.pt ZWAME Fórum 
To:  
Date: Tue, 22 Nov 2016 20:27:56 +0000 
Subject: Sacripanta started a conversation with you: "Recebeu um Aviso" 
 
yyyyyyyyyyya, Sacripanta começou uma conversa pessoal contigo em ZWAME Fórum:

"Recebeu um Aviso"

Esta é a mensagem colocada:
----------------------------------------------------------------------
yyyyyyyyyyya, informamos que recebeu um aviso pela forma como se dirigiu a outro membro.
Se necessitar de mais informação, leia as Regras do Fórum e utilize o Contacte o Staff.


----------
Vasila
----------
## Sim!!! A password é trocada uma vez por dia, pelo menos! Diria que 2 vezes por dia pelo menos (tenho de fazer mais testes para verificar)... GARANTO-TE a 100% que Fibra Meo SingleEgde que a password de Voip é trocada PELO MENOS uma vez por dia.... Sei exactamente como é o processo, mas não o vou divulgar em público.... Não te vou dizer se é um serviço automático da meo ou se é de outra forma qualquer, só te digo que sim, é TROCADA pelo menos diariamente...
----------
Tu nem sabes do que falas sequer. Estive a ler os teus post's anteriores e afirmo com toda a certeza, que nunca fizeste uma firmware na tua (curta) vida, bébé. E nunca usas-te um jtag. A tua ultima afirmação é sempre "mas não o vou divulgar em público....". Dizes que já crackaste as pass's do voip ("mas não o vou divulgar em público...."), mas nem sabes como se faz (muito menos como funciona). Só tretas..
Devias parar de postar coisas sem sentido (e sempre limitadas ao "mas não o vou divulgar em público...."), que a seguir contradizes derivado á tua incerteza. Quando não sabes, não falas (ou pelo menos, não devias).

----------
Vasila
----------
## Esquece... A meo não a vai dar porque também não sabe ;)
## Não, não podes usar a passwd fora da rede fibra meo, simplesmente não autentica, dá timeout! deve haver uma firewall pelo caminho que bloqueia pedidos de IPs que não seja MEO fibra... Nem MEO ADSL, nem MEO 4G na mesma zona geográfica funciona! Dá timeout.... Isto também é garantido, já testei!
----------
É o que eu digo.. Tu não sabes do que falas. Quando te digo para meteres lá a vlan12, continuas dentro da rede meo, e com IP portugues. Se precisares faço-te um desenho. Mas se aprenderes o que é uma vlan primeiro, vais entender. Até lá... bons estudos
""A meo tambem não a sabe"" ?? então quem sabe as pass's da meo? é a vodafone? Não sabem a actual, mas alteram para a que quiserem, e afinal (como que por magia) já sabem. Não???  mas tambem não sabias disso. Já nem importa, tás perdoado por tudo o que dizes



----------
## Faz toda a lógica não ter a cleartext neste caso!
## Quando querem conferir se a pass é a correcta apenas fazem match das cifras!
## Tu não envias cleartext quanto queres autenticar, envias sim a cifrada!
----------
Isso está certo, na possibilidade de funcionar como referi anteriormente. Não acredito muito que assim seja.
Mas o funcionamento normal é cleartext (que pode passar num tunnel cifrado, mas "sai" na outra ponta do tunnel e é confrontada contra o serviço em causa, já em cleartext (isto passa-se dentro do cpu do router claro). Mas no final entregas sempre cleartext ao serviço, ele calcula o MD5, e confronta-o com o MD5 que já tem guardado)     -----PS: ou pode nem ter de calcular o MD5, dependendo de como a meo armazena as nossas credenciais. Mas vamos partir do principio q estão encriptadas ;)



Já agora, vou dar ainda mais uma alternativa de sniffar a pass voip e que deve ser a mais acessivel para quem não tem os cabos serial.
1)Com o link da WAN - ONT ligado num switch ou hub, criar um servidor voip e configura-lo na mesma subnet da WAN
2)No thomson, alteram o endereço do servidor VOIP MEO para o IP que configuraram anteriormente.
3)Por ultimo, é ver os logins falhados e ver no LOG a password

É claro que o servidor tem de levar uns ajustes para isso, mas fica a ideia. So simple

Quem não tiver hub ou switch, é claro que podem ligar o vosso PC directo na WAN do router (se o souberem configurar), mas lembrem-se de primeiro ligar o router á meo para ele descarregar a configuração inicial e só depois é que alteram o IP do servidor voip para o do vosso PC. Na eventualidade do serviço voip não estar fidelizado á porta WAN (não posso confirmar), talvez seja ainda possivel configura-lo num IP da LAN. Queria ter aqui um thomson para confirmar isso, mas não. Vou arranjar um, e quando tiver tempo faço um tutorial das varias maneiras de se conseguir isso. Mas vai demora.........r
E acho que devemos discutir isto no git e ir guardando/actualizando os softwares e as configs que devem ser feitas
----------
----------------------------------------------------------------------

Para ver esta mensagem, clica aqui:
https://forum.zwame.pt/conversations/recebeu-um-aviso.2807849/unread

Para ver todas as mensagens pessoais activas, clica aqui:
https://forum.zwame.pt/conversations/

----------------------------------------------------------------------

Esta mensagem foi enviada do ZWAME Fórum porque as tuas preferências estão definidas para receber um email quando é recebida uma mensagem pessoal.

Para deixares de receber emails, por favor edita as preferências de contacto:
https://forum.zwame.pt/account/contact-details

https://forum.zwame.pt/
