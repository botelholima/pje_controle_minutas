PJe - Controle Pessoal de Minutas
Última atualização: 13 de novembro de 2026 · Aplicável à versão 1.5.0.
Esta política descreve as práticas da extensão independente PJe - Controle Pessoal de Minutas, desenvolvida por
@Botelho_Lima, destinada à organização pessoal do andamento de minutas no painel do Processo Judicial Eletrônico (PJe). A
integração visual desta versão foi desenvolvida para o painel do TRT da 3a Região.
1. Dados utilizados e finalidade
A extensão lê, na tabela de processos já exibida ao usuário autenticado, os números CNJ dos processos para vincular às
classificações pessoais Não iniciado, Em elaboração e Concluído. Também processa preferências de exibição, filtro, duração de
desbloqueio, datas técnicas de alteração e identificadores de dispositivos usados na sincronização. Os contadores e filtros
servem exclusivamente para organizar as marcações do usuário.
A extensão não consulta o conteúdo dos autos, não lê petições ou documentos judiciais para esse controle e não modifica
dados oficiais do PJe.
2. Proteção e armazenamento local
As marcações são mantidas no perfil do Chrome, em chrome.storage.local, dentro de um cofre cifrado com AES-256-GCM.
Uma chave aleatória protege os registros; essa chave é protegida por uma senha definida pelo usuário e, separadamente, por
um código de recuperação. A senha não é enviada para um servidor próprio nem armazenada em texto simples.
Para permitir desbloqueio automático pelo período escolhido, o navegador pode guardar material criptográfico protegido por uma
chave local não exportável no armazenamento IndexedDB do perfil da extensão. Isso não garante proteção contra pessoas com
controle do dispositivo, malware ou sessões já desbloqueadas.
3. Google Drive: sincronização opcional
Quando o usuário decide conectar uma conta Google e habilitar a sincronização, a extensão solicita autorização OAuth com o
escopo restrito drive.appdata. Os números CNJ, status e dados de marcação são criptografados no dispositivo antes
do envio à pasta privada appDataFolder da própria extensão, hospedada na infraestrutura do Google Drive.
A sincronização pode transmitir, além do conteúdo cifrado, metadados técnicos como identificador da instalação, identificação do
cofre, nome do arquivo e data de atualização. A extensão não solicita acesso geral aos demais documentos do Drive. O Google
processa os dados como fornecedor de infraestrutura de armazenamento de acordo com seus próprios termos e políticas.
A sincronização é desativada por padrão. Sem a autorização e ativação voluntárias, a extensão não envia sua base de
marcações ao Google Drive. A extensão não opera servidor próprio para receber esses registros.
4. Autenticação e permissões
A autenticação Google utiliza a API chrome.identity, que fornece um token OAuth para acessar apenas a área privada do
aplicativo. A extensão não pede nem armazena a senha da conta Google ou os códigos de dois fatores do PJe. A senha do cofre
é independente da conta Google.
As permissões storage, notifications, identity e alarms são utilizadas, respectivamente, para armazenar preferências e
o cofre, notificar atualizações, autorizar o Google Drive e agendar sincronizações quando habilitadas. O acesso ao domínio
www.googleapis.com serve exclusivamente às chamadas da API do Drive. O script de integração com o PJe atua somente em
https://pje.trt3.jus.br/pjekz/*, inserindo controles na rota do painel correspondente.

5. Compartilhamento e uso dos dados
Não vendemos informações dos usuários, não exibimos anúncios e não utilizamos os dados para publicidade, análise
comportamental, avaliação de crédito ou finalidades não relacionadas ao funcionamento do gerenciador de minutas. A
sincronização autorizada utiliza o Google Drive como infraestrutura de armazenamento; não há compartilhamento deliberado
com outros usuários.
6. Retenção, exclusão e recuperação
Os dados locais permanecem até que o usuário os remova ou que o navegador apague o armazenamento da extensão. Na
versão 1.5.0, a limpeza automática de registros de processos que deixam o painel não está habilitada, pois filtros e paginação
podem ocultar processos ainda ativos.
O botão “Desativar sincronização” interrompe novas sincronizações, mas não apaga automaticamente os arquivos já
armazenados no Google Drive. Para excluir os dados ocultos do aplicativo, o usuário pode consultar o Google Drive em
Configurações → Gerenciar aplicativos → Opções → Excluir dados ocultos de aplicativos, quando essa opção estiver
disponível. A extensão também oferece exportação de backup criptografado. Perder a senha e o código de recuperação pode
tornar a base irrecuperável.
7. Regras institucionais e independência
A extensão não é um produto oficial do Tribunal Regional do Trabalho da 3a Região, do CNJ ou do Poder Judiciário. O uso e,
especialmente, a sincronização em uma conta Google devem respeitar as normas institucionais de segurança e tratamento de
dados. A criptografia não substitui autorizações ou políticas internas.
8. Alterações e suporte
A política poderá ser atualizada quando mudarem os recursos, as permissões ou os tratamentos realizados. A versão vigente
será disponibilizada na Chrome Web Store. Para suporte, utilize os canais informados na página pública da extensão.
