# Drilling Fiscal Quick Form

Crie uma aplicação Web PWA completa em React com Vite para a empresa "Drilling do Brasil" (setor de escavação e fundação). O objetivo da aplicação é funcionar como um formulário ultra-rápido de pré-emissão de Nota Fiscal (Remessa/Reparo) e Conhecimento de Transporte (CTe), eliminando o recebimento de dados soltos via WhatsApp e telefone.

A aplicação precisa ser compilada para estáticos (pasta /dist) para rodar no frontend e enviar requisições para um backend em PHP nativo hospedado na HostGator (servidor compartilhado, sem Node.js em tempo de execução).

### 1. REQUISITOS TÉCNICOS & ARQUITETURA

- Frontend: React + Vite + Tailwind CSS (ou CSS inline responsivo e limpo).

- PWA: Configurar 'vite-plugin-pwa' com Service Worker e Web App Manifest para permitir instalação na tela inicial do celular e funcionamento offline/instável.

- Backend: PHP nativo na pasta `/api/salvar.php` para receber requisições multipart/form-data (JSON + arquivos), salvar arquivos de upload e gravar os dados em MySQL ou gerar log JSON/E-mail.

- Estilo do App: Mobile-first, botões grandes para toque no celular, visual moderno nas cores corporativas (tons de azul, vermelho/cinza industrial).

### 2. CAMPOS DO FORMULÁRIO (DESIGNED FOR SPEED)

O formulário deve ser preenchível em menos de 1 minuto no canteiro de obras:

1. Seletor Rápido de Transporte (Toggle/Buttons):

   - Frota Própria (Drilling)

   - Transportador Terceirizado (Exibe campos: Razão Social, CNPJ e ANTT/RNTRC).

2. Tipo de Operação (Dropdown simples):

   - Remessa de Ativo Imobilizado (Padrão/CFOP 6554)

   - Remessa para Conserto / Reparo

   - Retorno de Obra / Devolução

   - Retorno de Conserto / Reparo

   - Transferência entre Obras

3. Captura Rápida de Mídia (Inputs de Arquivo com 'capture="environment"'):

   - Tirar Foto/Upload da CNH do Motorista

   - Tirar Foto do Equipamento/Carregamento (Opcional)

4. Origem e Destino:

   - Origem: Dropdown com opções pré-cadastradas ("Pátio São José da Lapa - MG", "Obra Recife - PE", "Outro...")

   - Destino: Campo de texto curto para Nome da Obra e Endereço/Cidade.

5. Motorista e Veículo:

   - Nome do Motorista e CPF

   - Placa Cavalo (Tração) e Placa Carreta (Reboque/Prancha)

6. Lista Dinâmica de Carga/Equipamentos:

   - Tabela/Linhas dinâmicas para adicionar itens (Ex: "COMPLEMENTO DA FUWA GG09", "CAÇAMBA DE DENTE BAUER Ø 2200").

   - Campos por item: Descrição, Quantidade e Valor Estimado R$.

7. Totais e Observações:

   - Peso Bruto Total (em kg - padrão pré-preenchido ex: 16000)

   - Quantidade de Volumes (padrão pré-preenchido ex: 3)

   - Observações gerais.

### 3. RECURSOS ADICIONAIS NA INTERFACE

- Tela de Visualização "Espelho da Nota": Antes de enviar, exiba um resumo formatado tipo bloco de texto que possa ser copiado com 1 clique para colar no WhatsApp do setor fiscal.

- Suporte a Envio Offline: Se o usuário estiver sem internet, salve o pedido no LocalStorage e envie assim que a conexão voltar.

### 4. ESTRUTURA DE ARQUIVOS QUE PRECISO QUE VOCÊ GERE:

1. 'src/App.jsx': Componente principal com a lógica do formulário e toggle de etapas.

2. 'vite.config.js': Configurado com o 'vite-plugin-pwa'.

3. 'public/manifest.json': Configuração do PWA (ícones, nome 'Drilling Fiscal', cores).

4. 'api/salvar.php': Código PHP completo para upload dos anexos na HostGator e retorno do protocolo de confirmação.

5. '.htaccess': Arquivo para tratar o roteamento do React em hospedagens Apache/HostGator.

Construa a aplicação pronta para que eu possa rodar 'npm run build' e subir os arquivos para o cPanel da HostGator.

This project was built with [Lovable](https://lovable.dev).

## Build with Lovable

Continue developing this project in the [Lovable editor](https://lovable.dev/projects/8bda941d-6d0e-4b67-aca9-dcc43b12a9b3).

- **Ship faster**: describe what you want to build and Lovable handles the code.
- **Stay in sync**: every change made in Lovable is committed straight to this repository.
- **Full ownership**: this code is yours. Push to `main` on GitHub and your changes sync back into Lovable, ready for your next prompt.

## Development

Prefer working locally? You need Node.js and npm — [install with nvm](https://github.com/nvm-sh/nvm#installing-and-updating).

```sh
git clone <this-repository-url>
cd <repository-name>
npm i
npm run dev
```
