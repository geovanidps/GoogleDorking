
# 🕵️‍♂️ Google Dorking Cheat Sheet

## 📜 Descrição
Este documento contém uma lista abrangente de **Google Dorks**, que são consultas avançadas usadas para pesquisar informações sensíveis indexadas pelo Google. Essas técnicas são amplamente utilizadas por **pesquisadores de segurança** para identificar vulnerabilidades e por **profissionais de TI** para proteger suas infraestruturas. 

⚠️ **Atenção:** O uso inadequado dessas informações pode violar diretrizes legais e éticas. Utilize este material apenas para fins educacionais e de segurança. 🚀

## 📌 Informações Sensíveis
| **Dork** | **Descrição** |
|---------|-------------|
| `filetype:log intext:password` | Encontra arquivos de log com senhas vazadas |
| `filetype:sql intext:"INSERT INTO users"` | Bancos de dados SQL expostos |
| `filetype:conf inurl:server.conf` | Arquivos de configuração expostos |
| `intitle:"index of" "admin"` | Diretórios administrativos expostos |
| `ext:env intext:DB_PASSWORD` | Arquivos `.env` contendo credenciais |
| `filetype:json intext:API_KEY` | Chaves de API expostas em arquivos JSON |
| `filetype:config intext:secret` | Configurações que podem conter segredos |
| `filetype:xml intext:autodiscover` | Arquivos XML de Autodiscover do Exchange |

## 🔑 Credenciais Expostas
| **Dork** | **Descrição** |
|---------|-------------|
| `inurl:wp-config.php` | Configuração do WordPress com credenciais |
| `intitle:"Index of" "id_rsa"` | Chaves privadas SSH expostas |
| `filetype:ini intext:password` | Arquivos INI com senhas |
| `filetype:xml intext:AWSAccessKeyId` | Chaves da AWS expostas |
| `filetype:json intext:"client_secret"` | Segredos de OAuth vazados |
| `filetype:txt intext:"username" intext:"password"` | Arquivos de texto com credenciais |

## 🌎 Servidores Web e Protocolos Expostos
| **Dork** | **Descrição** |
|---------|-------------|
| `inurl:/phpinfo.php` | Arquivos `phpinfo.php` expostos |
| `intitle:"Apache Status" inurl:/server-status` | Status do Apache (pode revelar IPs internos) |
| `inurl:"/admin/login"` | Painéis administrativos expostos |
| `inurl:/wp-admin` | Login do WordPress |
| `inurl:/jenkins intext:"Dashboard"` | Jenkins CI/CD sem autenticação |
| `intitle:"Grafana" inurl:/login` | Painéis do Grafana desprotegidos |
| `filetype:conf intext:"NTLM"` | Configuração de NTLM potencialmente vulnerável |
| `intitle:"index of" "ntlm"` | Diretórios contendo arquivos relacionados ao NTLM |
| `filetype:config intext:"AuthenticationMethods"` | Métodos de autenticação configurados expostos |

## 🔥 Arquivos e Diretórios Sensíveis
| **Dork** | **Descrição** |
|---------|-------------|
| `intitle:"index of"` | Listagem de diretórios sem restrição |
| `intitle:"index of" "backup"` | Diretórios de backup públicos |
| `inurl:/backup/ filetype:zip` | Backups compactados expostos |
| `filetype:sql intext:"MySQL dump"` | Bancos de dados MySQL vazados |
| `filetype:bak OR filetype:old OR filetype:backup` | Arquivos de backup mal protegidos |

## ☁️ Descobertas em Docker, AWS e Azure
| **Dork** | **Descrição** |
|---------|-------------|
| `inurl:/docker/ intitle:"Index of"` | Imagens Docker expostas |
| `filetype:yml intext:"docker-compose"` | Arquivos `docker-compose.yml` expostos |
| `filetype:json intext:"aws_access_key_id"` | Chaves AWS expostas em JSON |
| `filetype:config intext:"azure"` | Configurações do Azure vazadas |
| `filetype:log intext:"azure_storage"` | Logs contendo segredos do Azure |
| `filetype:yaml intext:"gcp"` | Configurações do Google Cloud vazadas |
| `site:s3.amazonaws.com "index of"` | Buckets S3 públicos |
| `intitle:"Google Kubernetes Engine" inurl:/login` | Painéis do GKE expostos |
| `inurl:portainer intext:"Login"` | Portainer (gerenciamento de Docker) desprotegido |

## ⚡ Exploração de Open Redirect
| **Dork** | **Descrição** |
|---------|-------------|
| `inurl:(url= | return= | next= | redirect= | redir= | ret= | r2= | page=) inurl:http` | Parâmetros de redirecionamento potencialmente exploráveis |
| `site:example.com inurl:redirect?` | Teste de Open Redirect no domínio específico |

## 🖧 Serviços e Portas Expostas
| **Dork** | **Descrição** |
|---------|-------------|
| `intitle:"SSH" "Server banner"` | Servidores SSH expostos |
| `inurl:/smb/ intitle:"index of"` | Compartilhamentos SMB acessíveis |
| `inurl:/ftp/ intitle:"index of"` | Servidores FTP públicos |
| `inurl:/kibana intext:"Login"` | Kibana sem autenticação |
| `intitle:"SonarQube" inurl:/dashboard` | SonarQube aberto ao público |

## 🚀 Google Dorks para Bypass
| **Dork** | **Descrição** |
|---------|-------------|
| `site:example.com -www` | Ignora a versão `www` de um site |
| `cache:example.com` | Mostra versões antigas do site no cache do Google |
| `site:example.com intext:"password" OR intext:"senha"` | Busca por credenciais sem filtros |
| `allintext:admin login` | Busca por páginas de login administrativo |
| `inurl:login intext:dashboard` | Localiza páginas de login |
| `site:pastebin.com intext:"password"` | Busca credenciais vazadas no Pastebin |
| `site:github.com intext:"access_token"` | Tokens de acesso vazados no GitHub |

---
📌 **Nota:** Essas técnicas são para fins **educacionais e de segurança**. Use apenas com permissão. Não nós responsabilizamos por quaiquer danos🔥
