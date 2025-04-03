![Uploading Gemini_Generated_Image_9zrfoc9zrfoc9zrf.jpeg…]()


# 🕵️‍♂️ Google Dorking Cheat Sheet

## 📜 Descrição
Este documento contém uma lista abrangente de **Google Dorks**, que são consultas avançadas usadas para pesquisar informações sensíveis indexadas pelo Google. Essas técnicas são amplamente utilizadas por **pesquisadores de segurança** para identificar vulnerabilidades e por **profissionais de TI** para proteger suas infraestruturas. 

⚠️ **Atenção:** O uso inadequado dessas informações pode violar diretrizes legais e éticas. Utilize este material apenas para fins educacionais e de segurança. 🚀

## 🔥 Exploração de XSS, CSRF, LFI e Outras Vulnerabilidades
| **Dork** | **Descrição** |
|---------|-------------|
| `inurl:"search.php?q="` | Parâmetros vulneráveis a XSS |
| `inurl:".php?id="` | Possível parâmetro vulnerável a SQL Injection |
| `inurl:"/view.php?page="` | Possível vulnerabilidade de LFI (Local File Inclusion) |
| `inurl:"redirect.php?url="` | Parâmetro de redirecionamento suscetível a Open Redirect |
| `inurl:"/upload/" filetype:php` | Uploads de arquivos potencialmente exploráveis |
| `intitle:"Cross Site Request Forgery" inurl:"csrf"` | Páginas discutindo vulnerabilidades CSRF |
| `inurl:"/include/" intitle:"index of"` | Diretórios de includes expostos |
| `inurl:"config.json" intext:"secret"` | Arquivos de configuração com segredos expostos |

## 🔑 Credenciais Expostas
| **Dork** | **Descrição** |
|---------|-------------|
| `inurl:wp-config.php` | Configuração do WordPress com credenciais |
| `intitle:"Index of" "id_rsa"` | Chaves privadas SSH expostas |
| `filetype:ini intext:password` | Arquivos INI com senhas |
| `filetype:xml intext:AWSAccessKeyId` | Chaves da AWS expostas |
| `filetype:json intext:"client_secret"` | Segredos de OAuth vazados |
| `filetype:txt intext:"username" intext:"password"` | Arquivos de texto com credenciais |

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

## 🔍 Lista Única Adicional
| **Dork** | **Descrição** |
|---------|-------------|
| `intext:"Internal Server Error" OR intext:"SQL syntax error"` | Erros do servidor expostos |
| `inurl:login OR intext:"admin login"` | Páginas de login expostas |
| `inurl:"?id=" OR inurl:"?cat=" OR inurl:"?product="` | Parâmetros propensos a SQLi |
| `inurl:"upload" OR intext:"file upload"` | Pontos finais de upload de arquivo |
| `filetype:pdf OR filetype:doc OR filetype:xlsx` | Documentos sensíveis expostos |
| `inurl:"config" OR inurl:"settings" OR inurl:"credentials"` | Parâmetros sensíveis |
| `inurl:"redirect" OR inurl:"url="` | Redirecionamentos abertos e XSS divulgados |
| `site:github.com intext:"api_key" OR intext:"password"` | Vazamentos de código no GitHub |
| `ext:bak OR ext:old OR ext:backup` | Arquivos com extensões suculentas |
| `site:exemplo.com ext:txt ext:pdf` | Arquivos com documentos |




---
📌 **Nota:** Essas técnicas são para fins **educacionais e de segurança**. Use apenas com permissão. Não nós responsabilizamos por quaiquer danos🔥
