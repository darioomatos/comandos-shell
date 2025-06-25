
# 🧠 Comandos Avançados no Linux

> Lista viva e evolutiva de comandos úteis, com aplicação prática em **cibersegurança**, **administração de sistemas**, **redes** e **forense digital**.

---

## 📅 1. Ver data de instalação do sistema

```bash
stat -c %w /
```

🔹 Mostra a data de criação do sistema de arquivos root, útil para estimar a instalação do sistema.

**Exemplos:**
- Verificar reinstalações.
- Investigar compromissos recentes.
- Correlacionar com logs de boot inicial.

---

## 🔒 2. Atributos especiais de arquivos

```bash
lsattr
chattr
```

🔹 `lsattr` exibe atributos como imutável (`+i`). `chattr` os altera.

**Exemplos:**
- `chattr +i arquivo.conf`
- `lsattr /etc/*`
- Proteger arquivos críticos contra alteração.

---

## 🔍 3. Buscar arquivos e executar ação

```bash
find . -type f -name "*.log" -exec grep "ERRO" {} \;
```

🔹 Executa comandos em arquivos encontrados.

**Exemplos:**
- Buscar `.conf` e validar IPs.
- Aplicar `shellcheck` em `.sh`.
- Escanear arquivos suspeitos.

---

## 📼 4. Gravar a sessão do terminal

```bash
script sessao.log
```

🔹 Grava a sessão atual do shell.

**Exemplos:**
- Auditorias de shell.
- Provas em pentests.
- Revisões posteriores de comandos executados.

---

## 📚 5. Explicações rápidas de comandos

```bash
tldr netstat
whatis netstat
```

🔹 `tldr` fornece exemplos. `whatis` resume a função.

**Exemplos:**
- Estudo rápido de comandos esquecidos.
- Alternativa leve a manpages.
- Ideal para ambientes restritos.

---

## ❓ 6. Verificar existência de comandos

```bash
which nmap
whereis sshd
```

🔹 Localiza o caminho de comandos e binários.

**Exemplos:**
- Verificar presença de ferramentas.
- Identificar sobreposições via alias.
- Auditar instalação.

---

## 🔁 7. Repetir último comando

```bash
!!
```

🔹 Reexecuta o último comando digitado.

**Exemplos:**
- `sudo !!` após esquecer o sudo.
- Testar pequenas variações rapidamente.
- Scripts dinâmicos de histórico.

---

## 👤 8. Informações sobre usuários logados

```bash
who
whoami
```

🔹 Mostram usuários conectados e o usuário atual.

**Exemplos:**
- Detectar sessões SSH.
- Auditar terminais ativos.
- Scripts de identificação.

---

## 📄 9. Mostrar partes de arquivos longos

```bash
head -n 20 arquivo.log
tail -f arquivo.log
```

🔹 `head` mostra o início, `tail` o final.

**Exemplos:**
- Monitorar logs.
- Acompanhar alterações em tempo real.
- Análise rápida sem abrir o arquivo completo.

---

## 🔢 10. Contagens de texto

```bash
wc -l arquivo
wc -w arquivo
```

🔹 Conta linhas, palavras ou caracteres.

**Exemplos:**
- Medir tamanho de logs.
- Verificar comandos no `.bash_history`.
- Analisar arquivos manipulados.

---

## 📂 11. Ver arquivos abertos por processos

```bash
lsof
```

🔹 Lista todos os arquivos abertos, inclusive sockets.

**Exemplos:**
- `lsof -i :80`
- `lsof /etc/passwd`
- `lsof -u root`

---

## 🧠 12. Traçar chamadas de sistema

```bash
strace comando
```

🔹 Exibe chamadas de sistema do processo.

**Exemplos:**
- `strace curl google.com`
- `strace -e openat ls`
- Análise reversa e debugging.

---

## 💽 13. Ver uso de disco por diretório

```bash
du -sh *
```

🔹 Avalia consumo de espaço.

**Exemplos:**
- Identificar crescimento anormal.
- Localizar diretórios pesados.
- Gerenciar espaço em disco.

---

## 📡 14. Ver conexões e escuta de portas

```bash
ss -tuln
```

🔹 Exibe conexões TCP/UDP ativas.

**Exemplos:**
- Detectar bindshells.
- Verificar serviços ativos.
- `ss -tp` mostra PIDs.

---

## 🧬 15. Variáveis de ambiente

```bash
env
printenv
```

🔹 Lista variáveis exportadas.

**Exemplos:**
- Ver `LD_PRELOAD` ou tokens expostos.
- Comparar ambientes.
- Detecção de persistência via variável.

---

## 🦠 16. Localizar processos zumbis

```bash
ps aux | grep -E '[zZ]'
```

🔹 Identifica processos em estado de zumbi.

**Exemplos:**
- Pós-exploit.
- Detectar falhas de execução.
- Resposta a incidentes.

---

## 🏗️ 17. Listar módulos do kernel

```bash
lsmod
```

🔹 Mostra módulos carregados no kernel.

**Exemplos:**
- Buscar rootkits.
- `modinfo <módulo>` para detalhes.
- Auditar segurança do kernel.

---

## 🔐 18. Gerar hash de arquivos

```bash
sha256sum arquivo
```

🔹 Garante integridade de arquivos.

**Exemplos:**
- Comparar binários.
- Criar baseline.
- Verificar alterações.

---

## 👀 19. Monitorar tráfego em tempo real

```bash
iftop
```

🔹 Exibe tráfego de rede por IP.

**Exemplos:**
- Análise de conexões externas.
- Monitoramento de banda.
- Identificar comportamento anômalo.

---

## 🕵️ 20. Histórico de login

```bash
last
```

🔹 Mostra logins anteriores por IP e terminal.

**Exemplos:**
- Detectar acessos indevidos.
- Analisar origem de conexões.
- Correlacionar com incidentes.

---

📌 *Atualize este arquivo com novas descobertas laboratoriais e contribuições de campo.*
