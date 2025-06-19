# Gonx Spectre Edition V4.1

![gonx_spectre_bg](https://github.com/user-attachments/assets/6e98c4cb-7cc4-43a5-9928-a9f5fb57aa7e)


## Sua Plataforma Segura para Pesquisa e Navegação Anônima

Bem-vindo à **Gonx Spectre Edition V4.1**, uma distribuição Linux projetada para oferecer um ambiente robusto e discreto para suas atividades online. Esta distro foi otimizada para navegação anônima e equipada com um conjunto de ferramentas essenciais para segurança, privacidade e OSINT (Open Source Intelligence).

---

### Por Que Usar a Gonx Spectre Edition V4.1?

A **Gonx Spectre Edition V4.1** foi desenvolvida pensando em usuários que necessitam de um ambiente controlado para realizar pesquisas, acessar informações e operar online com um alto grau de privacidade. Ela se destaca por:

* **Anonimato Integrado**: Com o **Tor** pré-configurado e o **ProxyChains4**, suas conexões são roteadas através da rede Tor, dificultando o rastreamento da sua atividade online.
* **Ferramentas de Privacidade**: Inclui utilitários para limpeza de rastros, criptografia de dados e remoção de metadados, garantindo que suas ações permaneçam confidenciais.
* **Recursos de OSINT**: Pacotes como **Maigret**, **SpiderFoot**, **Sherlock**, **Recon-ng** e **theHarvester** transformam a Spectre em uma poderosa caixa de ferramentas para investigação e coleta de informações de fontes abertas.
* **Otimização e Leveza**: Partindo de um Debian Server minimalista, a distro foi "desinchada" de componentes desnecessários (como ambientes gráficos e serviços de impressão), resultando em um sistema leve e focado em desempenho.
* **Customização Avançada**: Com aliases de comando convenientes e um script de limpeza de rastros, a Spectre foi personalizada para ser intuitiva e eficiente.

---

### Credenciais de Acesso

* **Paasword para descriptografia**: `spectrepassword`
Recomendamos inicialmente mudar a senha padrão no virtualbox no campo > Geral > Criptografia de Disco
![image](https://github.com/user-attachments/assets/1c41bf89-9cea-41e5-8b7a-dcc001fdaf35)



Ao iniciar a máquina virtual, você acessará o TERMINAL. Use as seguintes credenciais:

* **Login**: `spectre`
* **Senha**: `spectre`

Para obter privilégios de `root`:

* Execute: `su -`
* **Senha Root**: `root`

---

### Primeiros Passos e Uso Básico

Após o login, você estará em um ambiente de linha de comando (CLI).

#### 1. Verificando o Anonimato com Tor e ProxyChains4

O serviço Tor já está habilitado e em execução. Você pode verificar seu status com:


> systemctl status tor

### Poderá taambém verificar com curl ou navegadores de terminal


> proxychains4 curl https://check.torproject.org



> proxychains4 lynx https://check.torproject.org

> proxychains4 elinks https://check.torproject.org

> proxychains4 w3m https://check.torproject.org

### Ou com funções para rotatividade de user agents


> gonxlynx https://check.torproject.org

> gonxelinks https://check.torproject.org

> gonxw3m https://check.torproject.org

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

Se o site indicar que você está conectado à rede Tor, a configuração está funcionando corretamente.

#### 2. Aliases de Comandos Úteis
Para facilitar seu trabalho, alguns aliases foram adicionados ao seu ~/.bashrc:

- ll: ls -l (lista detalhada)
- la: ls -la (lista detalhada incluindo arquivos ocultos)
- up: sudo apt update && sudo apt upgrade -y (atualiza e faz upgrade de pacotes)
- ssn: sudo shutdown -h now (desliga o sistema imediatamente)
- sshon: sudo systemctl start ssh (inicia o serviço SSH)
- sshoff: sudo systemctl stop ssh (para o serviço SSH)
- sshstat: sudo systemctl status ssh (verifica o status do serviço SSH)


Ferramentas de Anonimato e Privacidade
A Gonx Spectre vem com algumas ferramentas para proteger sua identidade e dados.

#### 3. Limpeza de Rastros com sensitive_clear.sh
Um script poderoso chamado sensitive_clear.sh está disponível em seu diretório home (~/.sensitive_clear.sh) para apagar logs do sistema, histórico de comandos e dados de navegadores terminal de forma segura usando shred, PORTANTO BAIXE E TRABALHE EM ARQUIVOS SENSÍVEIS NO DIRETÓRIO /tmp/sensitive, após suas atividades, basta executar o script de limpeza e sobrescrita.

Uso:

> sudo bash ~/.sensitive_clear.sh


Recomendação: Execute este script regularmente, especialmente antes de desligar ou após sessões de uso intensivo para garantir que nenhum rastro seja deixado.

#### 4. Outras Ferramentas de Privacidade e Segurança
cryptsetup: Ferramenta para gerenciar partições criptografadas (LUKS).
gnupg: Implementação do OpenPGP para criptografia e assinatura de dados.
wipe: Apaga arquivos de forma segura, impossibilitando recuperação.
secure-delete: Pacote que inclui ferramentas como srm (Secure Remove) para exclusão segura de arquivos e diretórios.
mat2: Uma ferramenta para remover metadados de arquivos (imagens, documentos, áudios, etc.).
Exemplo de uso: mat2 imagem.jpg
exiftool: Uma ferramenta para ler, gravar e editar metadados em diversos formatos de arquivos.
Exemplo de uso: exiftool -all= imagem.jpg (remove todos os metadados)
wireshark: Um analisador de protocolo de rede para capturar e inspecionar o tráfego de rede. Lembre-se de usá-lo com cautela e sob a devida permissão.
O usuário spectre já foi adicionado ao grupo wireshark para permitir a captura de pacotes.
Ferramentas de OSINT (Open Source Intelligence)
A Spectre Edition inclui um conjunto robusto de ferramentas OSINT, a maioria delas instaladas em ambientes virtuais (venv) para manter o sistema limpo e evitar conflitos de dependências. As ferramentas estão localizadas no diretório ~/osint-tools.

#### 5. Maigret (Busca de Nomes de Usuário em Redes Sociais)
Localização: ~/osint-tools/maigret

Ativação do Ambiente Virtual:

> cd ~/osint-tools/maigret
> source venv/bin/activate

Exemplo de Uso:

Para buscar um nome de usuário em diversas plataformas:

> maigret --proxy socks5://127.0.0.1:9050 nome_de_usuario

Nota: Sempre use o proxychains4 ou configure o proxy diretamente nas ferramentas para garantir que as requisições passem pelo Tor.

#### 6. SpiderFoot (Ferramenta de Reconhecimento Automatizada)
Localização: ~/osint-tools/spiderfoot

Ativação do Ambiente Virtual:

> cd ~/osint-tools/spiderfoot
> source venv/bin/activate

Uso (Interface de Linha de Comando):

> sudo sfcli.py

O sfcli.py é a interface de linha de comando do SpiderFoot. Para iniciar um scan:

> sfcli.py --target exemplo.com --modules all --level 3 --output file.json

Recomendação: Para uso completo do SpiderFoot com sua interface web, você precisaria de um ambiente gráfico e configurar o acesso via navegador, o que não é o foco desta distro. A versão CLI é útil para automação e scripts.

#### 7. Sherlock (Encontre Nomes de Usuário em Mais de 300 Redes Sociais)
Localização: ~/osint-tools/sherlock

Ativação do Ambiente Virtual:

> cd ~/osint-tools/sherlock
> source venv/bin/activate

Exemplo de Uso:

Para verificar a existência de um nome de usuário:

> proxychains4 sherlock nome_de_usuario

#### 8. Recon-ng (Framework de Reconhecimento)
Localização: ~/osint-tools/recon-ng

Ativação do Ambiente Virtual:

> cd ~/osint-tools/recon-ng
> source venv/bin/activate

Inicialização:

> ./recon-ng

Exemplos de Comandos dentro do Recon-ng:

Criar um workspace:
workspaces create myworkspace
Pesquisar módulos:
modules search domain
Carregar um módulo:
modules load recon/domains-hosts/google_site_web
Definir opções do módulo:
options set SOURCE example.com
Executar o módulo:
run

#### 9. theHarvester (Coleta de Informações de Subdomínios, E-mails, etc.)
Localização: ~/osint-tools/theHarvester

Ativação do Ambiente Virtual:

> cd ~/osint-tools/theHarvester
> source venv/bin/activate

Exemplo de Uso:

Para buscar e-mails e subdomínios de um domínio usando a fonte Google:


> proxychains4 theHarvester -d example.com -l 500 -b google


#### 10. Holehe (Verifica se um E-mail está Registrado em Sites)
Localização: ~/osint-tools/holehe

Ativação do Ambiente Virtual:

> cd ~/osint-tools/holehe
> source venv/bin/activate

Exemplo de Uso:

Para verificar se um e-mail está associado a serviços online:


> proxychains4 holehe usuario@exemplo.com

#### 11. Outras Ferramentas Incluídas

John (John the Ripper): Utilitário de cracking de senhas.
Exemplo: john --wordlist=rockyou.txt hash_file.txt
hashcat: O recuperador de senhas mais rápido e avançado do mundo.
Exemplo: hashcat -m 0 hash.txt passwordlist.txt (Para hashes MD5)
tmux: Multiplexador de terminal que permite gerenciar várias sessões de terminal em uma única janela. Essencial para manter processos rodando em segundo plano.
Comandos básicos: tmux (inicia uma nova sessão), Ctrl+b d (desanexa a sessão), tmux attach (reconecta à última sessão).
nmap: Scanner de rede para descoberta de hosts e portas.
Exemplo: proxychains4 nmap -sT -p 80,443 example.com (Scan de portas TCP via Tor)
netcat-traditional: Ferramenta de rede para leitura e escrita através de conexões de rede.
curl, wget: Ferramentas para transferência de dados com URLs.
git: Sistema de controle de versão para clonar repositórios.
htop: Monitor de processos interativo.
man-db: Banco de dados de páginas de manual para obter ajuda sobre comandos.
bash-completion: Habilita o auto-completar para comandos e argumentos no Bash.
Desinstalação e Limpeza de Pacotes
Caso precise remover um programa específico e limpar os rastros:


> sudo apt remove --purge <nome_do_programa>
> sudo apt autoremove
> sudo apt clean

Use sudo apt purge para remover o programa e seus arquivos de configuração. Em seguida, autoremove para remover dependências não utilizadas e clean para limpar o cache de pacotes baixados.

Função extract
Uma função extract foi adicionada ao seu ~/.bashrc para facilitar a descompactação de diversos tipos de arquivos.

Uso:

> extract <arquivo_compactado>

Exemplos:

> extract arquivo.tar.gz
> extract meu_documento.zip
> extract software.7z

Considerações Finais e Dicas de Segurança
A Gonx Spectre Edition V4.1 é uma ferramenta poderosa para privacidade e OSINT, mas lembre-se:

Nenhum sistema é 100% à prova de falhas: Sempre combine o uso desta distro com boas práticas de segurança, como senhas fortes e o uso consciente da internet.
Firewall (iptables): A distro inclui iptables. Considere configurar regras de firewall para restringir ainda mais o tráfego de saída e entrada, permitindo apenas o necessário para suas operações via Tor.
Atualizações: Mantenha o sistema atualizado com o comando up (ou sudo apt update && sudo apt upgrade -y) regularmente para garantir que você tenha as últimas correções de segurança e recursos.
Anonimato não é invencibilidade: O Tor ajuda no anonimato, mas suas ações ainda podem ser rastreadas se você não tomar cuidado (ex: fazer login em contas pessoais, usar informações de identificação).
Uso de VPN com Tor: Embora a distro inclua OpenVPN, o uso de VPN e Tor juntos pode ser complexo. Se não configurado corretamente (VPN-over-Tor ou Tor-over-VPN), pode comprometer sua privacidade em vez de aumentá-la. Para a maioria dos casos, o Tor por si só é suficiente para navegação anônima.


