# Projeto de Redes com Packet Tracer

Bem-vindo ao repositório do meu projeto de redes desenvolvido com Packet Tracer! Este projeto foi desenvolvido como proposta na UFCD de Redes do curso de Ciências Informáticas - Técnico/a de Informática - Sistemas, Nível 4, no IEFP em Portugal.

## Sobre o Projeto

Este projeto propõe uma solução de rede para a empresa fictícia TATRUP, especializada na venda de tratores. Utilizando a ferramenta Cisco Packet Tracer, foi simulado um ambiente hipotético que representa como seria apresentado um projeto inicial de redes para o cliente.

## Objetivo

O objetivo principal do projeto é criar, no simulador Packet Tracer, a rede a ser implementada para a empresa TATRUP. Isso inclui:

- Configuração do DHCP para atribuição dinâmica de endereços IP.
- Definição de servidores DNS para resolução de nomes.
- Implementação de acesso por HTTP para serviços web.
- Integração de dispositivos IoT para monitoramento.

## Estrutura do Repositório

Neste repositório, você encontrará:

- Diagramas de topologia da rede.
- Configurações detalhadas dos dispositivos no Packet Tracer.
- Documentação explicativa sobre as escolhas e configurações realizadas.

---

## Expecificações

<b>Cliente</b>: TATRUP, uma empresa especializada na venda de tratores.

<b>Objetivo</b>: Criar num simulador a rede a implementar (Packet Tracer) usando o DHCP, definir DNS, 
implementar acesso por HTTP e por IOT.

## Cenário hipotético

A empresa especializada na venda de tratores publicita os tratores num jornal local e é também referenciada como vendedora autorizada no Web site oficial da TRATS e nos maiores Web sites de venda de tratores. Quando um potencial cliente visita o “showroom” é recebido por um vendedor. O vendedor preenche manualmente um formulário com nome, morada, número de telefone, data da visita e a trator de interesse. O vendedor regista também a forma como o potencial cliente tomou conhecimento da empresa, jornal, Web,...

No showroom a ligação à internet é fraca o que implica por vezes que os vendedores usem os próprios telemóveis para fazerem registos ou mostrar as trators, não consegue aceder remotamente à base dados dos clientes para ver o seu histórico, nem fazer simulações de prestações no caso de um financiamento devido à lentidão da internet, é ainda comum conflitos entre vendedores por “roubo” de informação porque todos acedem ao mesmo ficheiro de Excel bem com estarem a ver filmes durante o horário de trabalho limitando a largura de banda que é de 50 Mb para todo o showroom.


Na área administrativa e logística os computadores são lentos a internet tem uma largura de banda de 2Mb, todos entram com a conta “Administrativo” e com a password “nuncamaisacaboisto” o que limita a saber quem fez o que bem como terem o ambiente de trabalho partilhado, não existe nenhuma drive para partilharem documentos que fazem através de uma pen de 64GB, a impressora é escrava do PC do Chefe que recebe os documentos por email ou por pen para imprimir, tem tido diversos problemas com vírus o que limita ainda mais a velocidade do trabalho. As reclamações dos clientes centram-se em falhas de comunicação com os vendedores porque muitas vezes escolhe a trator e a cor, na entrega chega outra cor devido que nos pequenos ecrãs dos telemóveis não se nota bem brilhos e outras características, lamentam ainda não haver impressão e que a espera é enorme e nem internet tem para irem pesquisando tendo de usar os próprios dados e por fim quando querem comprar a crédito só dois dias depois sabem o valor.

Mesmo com estas limitações a TATRUP teve uma subida dos negócios e decidiu comprar doispavilhões onde colocará toda a sua estrutura e departamentos. Os departamentos são Recursos humanos, Comercial, técnico e logístico.

No um é composto por uma área de 200m2 dividido em 6 gabinetes onde devem ter três postos de trabalho, uma impressora e uma ligação externa para os clientes que nos visitam. No dois é composto por uma área de 400m2 onde fica o showroom área de exposição e 4 postos para atendimento aos clientes.


Na empresa foi definido que os postos fixos teriam ips fixos e as ligações externas ips dinâmicos, existe um servidor que valida todos os acessos na empresa existindo vários tipos de utilizadores ou seja comercial, logística, gestor de operações…em que cada um deverá aceder apenas e só às aplicações que necessita bem como a uma drive de rede onde é partilhada documentação 
especifica. E um servidor dedicado para 10 webcams.

---

## Proposta Inicial: Situação Física

  - <b>Pavilhão 1</b>: 

    - 18 computadores (desktop)
    - 1 portátil (TI)
    - 6 impressoras
    - 6 telefones
    - 2 servidores sendo um para HTTP/DNS/DHCP e o outro para serviço IOT
    - 3 switches de 24 portas
    - 2 access points
    - 2 routers
    - 2 câmeras.


  - <b>Pavilhão 2</b>: 
    - 2 computadores (desktop)
    - 4 tablets (vendedores)
    - 2 impressoras
    - 2 telefones
    - 1 switch
    - 3 access points
    - 2 tvs
    - 8 câmeras.
    
## Proposta Inicial: Situação Lógica

Um meio encontrado para gerir a rede foi utilizar Vlans pois se todos os departamentos ficassem na mesma rede, poderíamos ter alguns problemas:
- A rede poderia ficar mais lenta com todos os computadores se comunicando pela mesma via, ao mesmo tempo;
- Por questão de segurança, pois um computador conseguiria "ver" o outro;
- Caso ocorresse algum tipo de problema em alguma parte da rede, todos os departamentos seriam afetados.

Então temos que configurar redes diferentes, cada uma relacionada a um departamento. Poderíamos configurar essas redes fisicamente separadas, isto é, com um switch para cada departamento, assim como uma interface no roteador. Porém o custo disso seria mais elevado, já que precisaríamos de mais switches e de um roteador com mais portas.

Por isso o ideal foi separar logicamente o switch e o roteador, pois assim, além de separarmos a rede entre os departamentos diversos, economizamos também.

---
                        
## Análise: Situação Lógica 

  - Topologia completa (Packet Tracer)</b>

![alt text](https://raw.github.com/NathSantos2024/Projeto_Redes/master/topologiacompleta.png)

   - Topologia pavilhão 1 (Packet Tracer)</b>

![alt text](https://raw.github.com/NathSantos2024/Projeto_Redes/master/topologiapavilhão1.png)

   - Topologia pavilhão 2 (Packet Tracer)</b>

![alt text](https://raw.github.com/NathSantos2024/Projeto_Redes/master/topologiapavilhão2.png)   

## Servidores
![alt text](https://raw.github.com/NathSantos2024/Projeto_Redes/master/ServidorHTTP_DNS_DHCP.png)

![alt text](https://raw.github.com/NathSantos2024/Projeto_Redes/master/ServidorIOT.png)

## VOIP
![alt text](https://raw.github.com/NathSantos2024/Projeto_Redes/master/VOIP.png)

## Apresentação do Projeto Final

Você pode baixar a apresentação do projeto final clicando [aqui](https://github.com/NathSantos2024/Projeto_Redes/blob/master/Apresenta%C3%A7%C3%A3o%20Projeto_Final.ppsx).


## Contribuições

Contribuições e sugestões são bem-vindas! Se você tiver alguma melhoria para sugerir ou encontrar algum problema, sinta-se à vontade para abrir uma *issue* ou enviar um *pull request*.

Obrigado por visitar o meu repositório do projeto de redes!

  


    
