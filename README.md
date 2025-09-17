# AWSCloudFormation
Este repositório tem como objetivo registrar os aprendizados adquiridos no desafio de AWS CloudFormation
# AWSCloudFormation
Este repositório tem como objetivo registrar os aprendizados adquiridos no desafio de AWS CloudFormation

🚀 Deploy de Infraestrutura AWS com CloudFormation

Este repositório contém exemplos de templates AWS CloudFormation para provisionamento automatizado de recursos relacionados a um cenário de e-commerce.

📋 Objetivo

O objetivo é demonstrar, de forma prática, como criar:

  Uma instância EC2 rodando Apache como servidor web.
  
  Uma VPC configurada para hospedar os recursos.
  
  Um Security Group com acesso HTTP e SSH liberado.
  
  Tudo de forma automatizada utilizando CloudFormation Stacks.

📂 Estrutura dos Templates

EC2.yaml / EC2.json → Template para provisionar uma instância EC2 com Apache configurado automaticamente.

Apache.json → Versão simplificada apenas para demonstrar a instalação do Apache em uma EC2.

🛠️ Passo a Passo
1. Acessar o CloudFormation

Vá até o console da AWS e abra o CloudFormation.

Clique em Criar pilha → Com novos recursos (padrão).
![alt text](/Imagens/criarPilha.png)

2. Upload do Template

Escolha Carregar um arquivo de modelo. Nesse repositório há arquivos modelo de Apache e EC2 lembre se sempre usar o mesmo tipo de versão como json ou yaml

Faça o upload do arquivo EC2.yaml (ou EC2.json).
![alt text](/Imagens/uploadEC2.png)

3. Revisar Infraestrutura

Após o upload, você pode:

Visualizar graficamente no Designer do CloudFormation.
![alt text](/Imagens/caminhoVisualizarGraficamente.png)
![alt text](/Imagens/visualizarGraficamente.png)

Editar manualmente arrastando os componentes.

Alterar diretamente no código na aba Modelo.
![alt text](/Imagens/abaModelo.png)

4. Configurar a Pilha

Dê um nome para a pilha (exemplo: Ecommerce-Stack).
![alt text](/Imagens/configPilha.png)

Selecione os parâmetros desejados (como tipo da instância EC2).

Clique em Avançar até a tela de revisão.

Confirme e clique em Criar pilha.
![alt text](/Imagens/criarPilha.png)
![alt text](/Imagens/pilhaCriada.png)

5. Outputs da Pilha

Após a criação, o CloudFormation exibirá as saídas configuradas:

InstanceId → ID da instância criada.

PublicIP → IP público da EC2.

WebURL → URL HTTP para acessar o Apache.

Exemplo de acesso no navegador:

http://<PublicIP>

6. Criando Servidor Apache

Caso queira apenas uma EC2 rodando Apache (sem VPC customizada), basta fazer upload do arquivo Apache.json, que contém uma versão simplificada.

✅ Resultado Esperado

Ao acessar o PublicIP ou a WebURL gerada, você verá a página inicial com a mensagem:

Servidor do E-commerce rodando na EC2 🚀

⚠️ Observações

O template usa AMI Amazon Linux 2 (ami-08c40ec9ead489470). Verifique se está disponível na sua região antes do deploy.

As portas 22 (SSH) e 80 (HTTP) estão liberadas para todos os IPs (0.0.0.0/0).

Para uso em produção, recomenda-se restringir o acesso ao SSH apenas ao seu IP.