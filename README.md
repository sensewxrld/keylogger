# keylogger

Keylogger Furtivo (Versão de Log Local)
Esta versão foca na furtividade e na persistência dos dados localmente:

Ação: O keylogger monitora e registra cada tecla digitada pelo usuário (incluindo senhas, mensagens e pesquisas) em um arquivo de log secreto ou oculto no próprio sistema comprometido.

Furtividade: Ele é projetado para operar em segundo plano (em background), sem abrir janelas ou criar processos óbvios. A chave aqui é o armazenamento local, que reduz o tráfego de rede incomum, tornando a detecção pelo firewall mais difícil.

Exfiltração (Manual): O atacante precisaria acessar o host novamente (usando a sessão do Meterpreter, por exemplo) para transferir o arquivo de log acumulado para o seu próprio sistema.

2. Keylogger Ativo (Versão de Email)
Esta versão prioriza a agilidade na exfiltração e o acesso em tempo real aos dados:

Ação: Além de registrar as teclas, o keylogger estabelece uma conexão de rede para enviar os dados.

Transmissão Programada: O script coleta as teclas digitadas e, a cada 60 segundos, empacota o conteúdo e o envia para um email de teste (ou outro servidor de coleta de dados).

Detecção: Esta versão é mais vulnerável à detecção por dois motivos:

O Firewall pode alertar sobre um aplicativo desconhecido que está tentando se conectar a um serviço de email (SMTP).

As ferramentas de segurança modernas podem identificar o padrão de tráfego recorrente e suspeito (a cada 60 segundos) sendo enviado para um destino não relacionado ao aplicativo legítimo.

Lição da Simulação
A criação dessas duas versões demonstra que o atacante sempre pondera entre furtividade (log local) e rapidez na coleta de dados (log por email).

Para nós, a defesa é clara:

Versão Furtiva: Exige monitoramento de comportamento (se o malware tentar ler ou modificar arquivos de log).

Versão Ativa: Exige firewall e monitoramento de rede para bloquear as tentativas de conexão de saída (a exfiltração via email).
