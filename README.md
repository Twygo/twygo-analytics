# Twygo Analytics — guia de instalação

Aplicativo para Windows com os painéis de aprendizagem do seu ambiente Twygo.
Ele roda **na sua máquina** e consulta a API Twygo diretamente: nenhum dado passa
por servidores intermediários.

---

## 1. Baixar

Baixe o instalador na página de versões do projeto:

**[⬇️ Baixar a versão mais recente](https://github.com/Twygo/twygo-analytics/releases/latest)**

O arquivo se chama `Twygo-Analytics-Setup-1.0.2.exe` (cerca de 170 MB).

---

## 2. Instalar

1. Dê **duplo clique** no arquivo baixado.
2. O Windows pode exibir um aviso de **"aplicativo não reconhecido"** — isso
   acontece porque o instalador ainda não tem assinatura digital. Clique em
   **Mais informações → Executar assim mesmo**.

   Se quiser conferir a integridade do arquivo antes, compare o hash publicado
   no release com o do seu download:

   ```powershell
   Get-FileHash .\Twygo-Analytics-Setup-1.0.2.exe -Algorithm SHA256
   ```
3. Escolha a pasta de instalação (ou aceite a sugerida) e conclua.
4. O atalho **Twygo Analytics** aparece na Área de Trabalho e no Menu Iniciar.

> Não é necessário instalar Node.js, Power BI nem qualquer outro programa: tudo
> vem embutido no aplicativo.

---

## 3. Primeiro acesso

Existem dois tipos de instalador, e o comportamento na primeira abertura depende
de qual você recebeu.

### Se o instalador foi preparado para o seu ambiente

É o caso quando o nome do arquivo traz o nome da sua empresa, por exemplo
`Twygo-Analytics-Acme-1.0.2.exe`.

**Não há nada a configurar.** O aplicativo já sabe de onde ler os dados: abra e
os painéis carregam. A primeira carga leva de 10 a 40 segundos, buscando os dados
da API; depois vem do cache local e as aberturas seguintes são imediatas.

### Se o instalador é a versão genérica

É o caso do arquivo `Twygo-Analytics-Setup-1.0.2.exe`. Na primeira abertura ele
pede duas informações:

| Campo | O que informar |
|---|---|
| **URL da API** | Deixe `https://api.twygo.com/api/v2`, salvo se o seu ambiente usar outro endereço |
| **Chave da API** | A chave do seu ambiente Twygo |

Clique em **Conectar e começar**. O aplicativo testa a conexão antes de salvar —
se a chave estiver errada, ele avisa na hora em vez de falhar depois.

Isso é pedido **uma única vez**. Nas próximas aberturas o aplicativo já entra
direto nos painéis.

**Onde conseguir a chave:** no painel administrativo do seu ambiente Twygo, na
área de integrações/API. Se você não tiver acesso, peça ao administrador do
ambiente.

---

## 4. Usando os painéis

O menu lateral tem 21 telas organizadas por área:

- **Aprendizagem** — Certificados, Progresso, Carga horária, Cursos mais
  concluídos, Acessos em atividades, Vigência de inscrição, Histórico
- **Trilhas** — execução das trilhas por usuário (trilha → curso → inscrito)
- **Questionários** — Resultados, Respostas por aluno, Respostas por pergunta
- **Pessoas** — Ficha do inscrito, Novos usuários, Usuários sem inscrição,
  Cursos não iniciados
- **Engajamento** — Ranking, Ranking por empresa, Curtidas, Descurtidas,
  Salvamentos

Em todas as telas você tem:

- **Filtros** no topo (período, curso, usuário, empresa, área, ambiente) que
  valem para tudo que está abaixo;
- **Clique nos gráficos** para filtrar o painel inteiro — clicar de novo desfaz;
- **Exportação CSV** nas tabelas, pronta para abrir no Excel;
- **Tema claro e escuro**, no botão do canto superior direito.

---

## 5. Atualização dos dados

Os painéis leem de um **cache local**, por isso abrem instantaneamente. A busca
na API acontece em segundo plano.

No ícone de **atualização** (🔄, canto superior direito) você encontra:

- quando cada conjunto de dados foi buscado da API pela última vez;
- botão para **atualizar tudo agora** ou apenas um conjunto;
- configuração da **frequência de atualização automática** (1, 3, 6, 12 ou 24
  horas — o padrão é 6);
- opção de limpar o cache.

A primeira carga de cada conjunto leva de 10 a 40 segundos, porque percorre a API
página por página. Depois disso fica em cache e a navegação é imediata, mesmo se
você fechar e reabrir o aplicativo.

---

## 6. Trocar de ambiente ou de chave

No ícone de **engrenagem** (⚙️, canto superior direito) você pode alterar a URL e
a chave da API — vale também para os instaladores já preparados, caso a chave do
seu ambiente mude. Ao trocar de ambiente, o cache é limpo automaticamente para
não misturar dados.

Atualizar o aplicativo **não desfaz** alterações feitas aqui.

---

## Perguntas frequentes

**Meus dados vão para a nuvem?**
Não. O aplicativo roda na sua máquina e fala apenas com a API Twygo. O cache e a
chave ficam gravados localmente, em `%APPDATA%\Twygo Analytics`.

**Como atualizo para uma versão nova?**
Baixe o instalador da versão nova e execute — ele atualiza a instalação
existente. Suas credenciais e o cache são preservados.

**Preciso de licença do Power BI?**
Não. Este aplicativo substitui o template Power BI e não depende dele.

**Posso instalar em vários computadores?**
Sim. Se o instalador foi preparado para o seu ambiente, cada máquina já abre
configurada; na versão genérica, cada instalação pede a chave uma vez.

**Como desinstalo?**
Configurações do Windows → Aplicativos → Twygo Analytics → Desinstalar. Os dados
locais (cache e chave) permanecem em `%APPDATA%\Twygo Analytics`; apague essa
pasta se quiser remover tudo.

**O antivírus bloqueou o instalador.**
Como o instalador não tem assinatura digital, alguns antivírus são
conservadores. Baixe sempre pela página de versões oficial (link acima) e
libere o arquivo se necessário.

**A tela fica com blocos cinza ao abrir.**
É a primeira busca dos dados na API. Aguarde de 10 a 40 segundos — nas próximas
vezes vem do cache.

---

## Suporte

Dúvidas ou problemas na instalação? Fale com o seu contato na Twygo.

<sub>Twygo Analytics — desenvolvido pela [Twygo](https://twygo.com).</sub>
