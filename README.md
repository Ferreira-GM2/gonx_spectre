# Gonx Spectre Edition V4.1

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

```bash
systemctl status tor
