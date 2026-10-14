# Awesome Análise de Malware [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> Uma lista curada de ferramentas, frameworks e recursos para **análise de malware**, **engenharia reversa**, **forense de memória**, **threat intelligence**, **detecção com IA** e **resposta a incidentes**.

Esta é uma versão **revisada e atualizada** da clássica `awesome-malware-analysis`, mantida originalmente por [@rshipp](https://github.com/rshipp). O objetivo desta revisão é:

- **Remover** ferramentas e serviços descontinuados ou sem manutenção.
- **Adicionar** ferramentas modernas que se tornaram padrão na comunidade.
- **Incluir** uma seção dedicada a **IA e LLMs aplicados à análise de malware**.
- **Indicar** o status de manutenção de cada ferramenta com marcadores de status.
- Manter a **estrutura de categorias** clara e útil que consagrou a lista original.

**Legenda de status:**
- 🟢 **Ativo** — Mantido ativamente (commits nos últimos 6 meses)
- 🟡 **Estável** — Funcional, mas com manutenção lenta ou intermitente
- 🔴 **Arquivado/Descontinuado** — Não recebe mais atualizações
- 🆕 **Novo** — Adicionado nesta revisão
- 🤖 **IA/LLM** — Integra inteligência artificial ou modelos de linguagem

---

## Índice

- [Coleta de Malware](#coleta-de-malware)
    - [Anonimizadores](#anonimizadores)
    - [Honeypots](#honeypots)
    - [Corpora de Malware](#corpora-de-malware)
- [Threat Intelligence Open Source](#threat-intelligence-open-source)
    - [Ferramentas](#ferramentas)
    - [Outros Recursos](#outros-recursos)
- [Detecção e Classificação](#detecção-e-classificação)
- [Scanners Online e Sandboxes](#scanners-online-e-sandboxes)
- [Análise de Domínio](#análise-de-domínio)
- [Malware de Navegador](#malware-de-navegador)
- [Documentos e Shellcode](#documentos-e-shellcode)
- [File Carving](#file-carving)
- [Desobfuscação](#desobfuscação)
- [Debug e Engenharia Reversa](#debug-e-engenharia-reversa)
- [Rede](#rede)
- [Forense de Memória](#forense-de-memória)
- [Artefatos do Windows](#artefatos-do-windows)
- [Armazenamento e Workflow](#armazenamento-e-workflow)
- [🤖 IA e LLMs para Análise de Malware](#-ia-e-llms-para-análise-de-malware)
- [Miscelânea](#miscelânea)
- [Recursos](#recursos)
    - [Livros](#livros)
    - [Outros](#outros)
- [Listas Awesome Relacionadas](#listas-awesome-relacionadas)
- [Contribuindo](#contribuindo)
- [Agradecimentos](#agradecimentos)

---

## Coleta de Malware

### Anonimizadores

*Anonimizadores de tráfego web para analistas.*

- 🟢 [Tor](https://www.torproject.org/) — O Onion Router, para navegar na web sem deixar rastros do IP do cliente. **Análise:** Padrão absoluto para anonimato em pesquisa de malware. Continua essencial.
- 🟢 [OpenVPN](https://openvpn.net/) — Soluções de software e hospedagem VPN. **Análise:** Robusto e amplamente utilizado, mas a versão Community tem limitações em relação à versão comercial.
- 🟡 [Privoxy](https://www.privoxy.org/) — Servidor proxy open source com recursos de privacidade. **Análise:** Estável, mas com desenvolvimento lento. Ainda funcional para cenários específicos de proxy.

### Honeypots

*Capture e colete suas próprias amostras.*

- 🟢 [Cowrie](https://github.com/cowrie/cowrie) — Honeypot SSH/Telnet, baseado no Kippo. **Análise:** Excelente para capturar ataques de força bruta e explorar interações SSH maliciosas. Ativo e bem documentado.
- 🟢 [Dionaea](https://github.com/DinoTools/dionaea) — Honeypot projetado para capturar malware. **Análise:** Um dos honeypots mais maduros para captura de malware multi-protocolo. Mantido ativamente.
- 🟢 [Conpot](https://github.com/mushorg/conpot) — Honeypot ICS/SCADA. **Análise:** Nichado, mas essencial para ambientes industriais. Mantido pelo MushMush.
- 🟢 [Thug](https://github.com/buffer/thug) — Honeyclient de baixa interação para investigar sites maliciosos. **Análise:** Ferramenta de nicho poderosa para análise de drive-by downloads. Mantida.
- 🟡 [Glastopf](https://github.com/mushorg/glastopf) — Honeypot de aplicações web. **Análise:** Funcional, mas com desenvolvimento mais lento. Ainda útil para capturar ataques web.
- 🟡 [Honeytrap](https://github.com/honeytrap/honeytrap) — Sistema open source para executar, monitorar e gerenciar honeypots. **Análise:** Bom framework de orquestração, mas com comunidade menor.
- 🟡 [MHN](https://github.com/pwnlandia/mhn) — Servidor centralizado para gerenciamento e coleta de dados de honeypots. **Análise:** Útil para ambientes com múltiplos sensores, mas interface datada.
- 🟡 [HoneyDrive](https://bruteforce.gr/honeydrive/) — Distro Linux com bundle de honeypots. **Análise:** Prático para iniciantes, mas a distro base está desatualizada.
- 🟡 [Mnemosyne](https://github.com/johnnykv/mnemosyne) — Normalizador de dados de honeypot, suporta Dionaea. **Análise:** Nichado, útil para padronizar dados.
- 🟡 [DemoHunter](https://github.com/RevengeComing/DemonHunter) — Honeypots distribuídos de baixa interação. **Análise:** Menos conhecido, mas funcional para cenários distribuídos.


### Corpora de Malware

*Amostras de malware coletadas para análise.*

- 🟢 [Malpedia](https://malpedia.caad.fkie.fraunhofer.de/) — Recurso que fornece identificação rápida e contexto acionável para investigações de malware. **Análise:** Um dos melhores recursos para pesquisa de famílias de malware. Mantido pelo Fraunhofer FKIE.
- 🟢 [VirusShare](https://virusshare.com/) — Repositório de malware, requer cadastro. **Análise:** O maior repositório público de amostras. Indispensável.
- 🟢 [MalwareBazaar](https://bazaar.abuse.ch/) — 🆕 Plataforma da abuse.ch para compartilhamento de amostras de malware. **Análise:** Excelente complemento ao VirusShare, com curadoria mais recente.
- 🟢 [Malshare](https://malshare.com) — Grande repositório de malware ativamente coletado de sites maliciosos. **Análise:** API robusta, amostras frescas.
- 🟢 [VX Underground](https://vx-underground.org/) — Coleção massiva e crescente de amostras de malware gratuitas. **Análise:** Principal fonte da comunidade para amostras e papers.
- 🟢 [theZoo](https://github.com/ytisf/theZoo) — Amostras de malware vivas para analistas. **Análise:** Bem organizado, útil para treinamento.
- 🟢 [Contagio](https://contagiodump.blogspot.com/) — Coleção de amostras e análises recentes. **Análise:** Blog histórico com análises detalhadas. Ainda relevante.
- 🟢 [InQuest Labs](https://labs.inquest.net) — Corpus pesquisável de documentos maliciosos do Microsoft Office. **Análise:** Nichado e extremamente útil para análise de maldocs.
- 🟢 [Javascript Malware Collection](https://github.com/HynekPetrak/javascript-malware-collection) — Coleção de quase 40.000 amostras de malware JavaScript. **Análise:** Recurso único para análise de malware web.
- 🟢 [Exploit Database](https://www.exploit-db.com/) — Amostras de exploits e shellcode. **Análise:** Referência clássica, mantida pela Offensive Security.
- 🟢 [Infosec - CERT-PA](https://infosec.cert-pa.it/analyze/submission.html) — Coleta e análise de amostras de malware. **Análise:** Recurso italiano bem mantido.
- 🟡 [Clean MX](http://support.clean-mx.com/clean-mx/viruses.php) — Banco de dados em tempo real de malware e domínios maliciosos. **Análise:** Útil, mas interface datada.
- 🟡 [Ragpicker](https://github.com/robbyFux/Ragpicker) — Crawler de malware baseado em plugins com funcionalidades de pré-análise e relatórios. **Análise:** Ferramenta de nicho, útil para automação de coleta.
- 🟡 [Tracker h3x](http://tracker.h3x.eu/) — Agregador para rastreamento de corpus de malware e sites de download maliciosos. **Análise:** Recurso útil, mas manutenção irregular.
- 🟡 [VirusBay](https://beta.virusbay.io/) — Repositório comunitário de malware e rede social. **Análise:** Ainda em beta, comunidade pequena.
- 🟡 [ViruSign](http://www.virussign.com/) — Banco de dados de malware detectado por muitos antivírus, exceto ClamAV. **Análise:** Nichado, útil para testar detecção.
- 🟡 [VX Vault](http://vxvault.net) — Coleção ativa de amostras de malware. **Análise:** Fonte secundária, útil como complemento.
- 🟡 [vduddu malware repo](https://github.com/vduddu/Malware) — Coleção de vários arquivos de malware e código-fonte. **Análise:** Pequeno, mas útil para exemplos.
- 🟡 [Zeus Source Code](https://github.com/Visgean/Zeus) — Código-fonte do trojan Zeus vazado em 2011. **Análise:** Valor histórico e educacional.
- 🟡 [Zeltser's Sources](https://zeltser.com/malware-sample-sources/) — Lista de fontes de amostras organizada por Lenny Zeltser. **Análise:** Excelente recurso meta, mantido por referência da área.

---

## Threat Intelligence Open Source

### Ferramentas

*Colete e analise IOCs.*

- 🟢 [MISP](https://github.com/MISP/MISP) — Plataforma de Compartilhamento de Informações sobre Malware. **Análise:** Padrão de facto para compartilhamento de threat intelligence. Ativo e amplamente adotado.
- 🟢 [Pulsedive](https://pulsedive.com) — Plataforma de threat intelligence comunitária e gratuita que coleta IOCs de feeds open-source. **Análise:** Excelente interface, API generosa no plano gratuito.
- 🟢 [ThreatIngestor](https://github.com/InQuest/ThreatIngestor/) — Construa pipelines automatizados de threat intel a partir de Twitter, RSS, GitHub e mais. **Análise:** Extremamente flexível e bem mantido pela InQuest.
- 🟢 [IntelMQ](https://github.com/certtools/intelmq) — Ferramenta para CERTs processarem dados de incidentes usando fila de mensagens. **Análise:** Robusto, mantido pela comunidade CERT.
- 🟢 [iocextract](https://github.com/InQuest/python-iocextract) — Extrator avançado de Indicadores de Compromisso (IOC), biblioteca Python e ferramenta de linha de comando. **Análise:** Simples e eficaz.
- 🟢 [AlienVault Open Threat Exchange](https://otx.alienvault.com/) — Compartilhe e colabore no desenvolvimento de Threat Intelligence. **Análise:** Grande comunidade, feeds úteis.
- 🟢 [MISP](https://github.com/MISP/MISP) — Plataforma de Compartilhamento de Informações sobre Malware. **Análise:** Padrão de facto.
- 🟢 [ThreatConnect](https://threatconnect.com/free/) — TC Open permite ver e compartilhar dados de ameaças open source. **Análise:** Plano gratuito útil para pequenas equipes.
- 🟢 [ThreatCrowd](https://www.threatcrowd.org/) — Motor de busca para ameaças com visualização gráfica. **Análise:** Útil para investigações rápidas, mas com desenvolvimento lento.
- 🟢 [RiskIQ](https://community.riskiq.com/) — Pesquise, conecte, marque e compartilhe IPs e domínios. **Análise:** Antigo PassiveTotal, agora parte da Microsoft. Ainda muito útil.
- 🟢 [YETI](https://github.com/yeti-platform/yeti) — Plataforma para organizar observáveis, IOCs, TTPs e conhecimento sobre ameaças em um repositório unificado. **Análise:** Excelente para equipes de threat intel.
- 🟡 [AbuseHelper](https://github.com/abusesa/abusehelper) — Framework open source para receber e redistribuir feeds de abuso e threat intel. **Análise:** Funcional, mas com desenvolvimento lento.
- 🟡 [Combine](https://github.com/mlsecproject/combine) — Ferramenta para coletar indicadores de Threat Intelligence de fontes públicas. **Análise:** Útil, mas manutenção intermitente.
- 🟡 [Fileintel](https://github.com/keithjjones/fileintel) — Obtenha inteligência por hash de arquivo. **Análise:** Nichado, funcional.
- 🟡 [Hostintel](https://github.com/keithjjones/hostintel) — Obtenha inteligência por host. **Análise:** Nichado, funcional.
- 🟡 [IOC Editor](https://www.fireeye.com/services/freeware/ioc-editor.html) — Editor gratuito para arquivos IOC XML. **Análise:** Legado, mas ainda usado.
- 🟡 [ioc_writer](https://github.com/mandiant/ioc_writer) — Biblioteca Python para trabalhar com objetos OpenIOC. **Análise:** Útil para automação.
- 🟡 [MalPipe](https://github.com/silascutler/MalPipe) — Motor de ingestão e processamento de malware/IOC que enriquece dados coletados. **Análise:** Pipeline útil, mas com desenvolvimento lento.
- 🟡 [Massive Octo Spice](https://github.com/csirtgadgets/massive-octo-spice) — Agrega IOCs de várias listas. **Análise:** Antigo CIF, ainda funcional.
- 🟡 [PyIOCe](https://github.com/pidydx/PyIOCe) — Editor OpenIOC em Python. **Análise:** Nichado.
- 🟡 [threataggregator](https://github.com/jpsenior/threataggregator) — Agrega ameaças de segurança de várias fontes. **Análise:** Script simples.
- 🟡 [ThreatTracker](https://github.com/michael-yip/ThreatTracker) — Script Python para monitorar e gerar alertas com base em IOCs. **Análise:** Simples, mas funcional.
- 🟡 [TIQ-test](https://github.com/mlsecproject/tiq-test) — Visualização de dados e análise estatística de feeds de Threat Intelligence. **Análise:** Ferramenta de pesquisa.

> **Removidos por desatualização:** `Cymon` (descontinuado), `ZeuS Tracker` (abuse.ch descontinuou o serviço).

### Outros Recursos

*Recursos de threat intelligence e IOCs.*

- 🟢 [Yara rules](https://github.com/Yara-Rules/rules) — Repositório de regras Yara. **Análise:** Grande coleção, mas precisa de curadoria.
- 🟢 [abuse.ch](https://abuse.ch/) — 🆕 Plataforma suíça com múltiplos serviços: MalwareBazaar, ThreatFox, URLhaus, Feodo Tracker. **Análise:** Um dos recursos mais confiáveis e ativos para IOCs. Essencial.
- 🟢 [FireHOL IP Lists](https://iplists.firehol.org/) — Análise de mais de 350 listas de IP com foco em ataques, malware e abuso. **Análise:** Excelente recurso analítico.
- 🟢 [InQuest REPdb](https://labs.inquest.net/repdb) — Agregação contínua de IOCs de várias fontes de reputação abertas. **Análise:** Muito útil, mantido pela InQuest.
- 🟢 [InQuest IOCdb](https://labs.inquest.net/iocdb) — Agregação contínua de IOCs de blogs, repos GitHub e Twitter. **Análise:** Complementar ao REPdb.
- 🟢 [Internet Storm Center (DShield)](https://isc.sans.edu/) — Diário e banco de dados pesquisável de incidentes, com API web. **Análise:** Recurso clássico da SANS, ativo há décadas.
- 🟢 [Proofpoint Threat Intelligence](https://www.proofpoint.com/us/products/et-intelligence) — Conjuntos de regras e mais. **Análise:** Antigo Emerging Threats, referência em regras Suricata.
- 🟢 [STIX/TAXII](https://oasis-open.github.io/cti-documentation/) — Linguagem padronizada para representar e compartilhar informações de ameaças cibernéticas. **Análise:** Padrão da indústria, mantido pela OASIS.
- 🟢 [ThreatMiner](https://www.threatminer.org/) — Portal de mineração de dados para threat intelligence com busca. **Análise:** Útil para pesquisa.
- 🟢 [threatRECON](https://threatrecon.co/) — Busque indicadores, até 1000 gratuitos por mês. **Análise:** Plano gratuito útil.
- 🟢 [ThreatFox](https://threatfox.abuse.ch/) — 🆕 Plataforma da abuse.ch para compartilhamento de IOCs. **Análise:** Foco em IOCs de C2 e malware. Excelente.
- 🟡 [Autoshun](https://www.autoshun.org/) ([list](https://www.autoshun.org/files/shunlist.csv)) — Plugin Snort e blocklist. **Análise:** Funcional, mas com manutenção irregular.
- 🟡 [Bambenek Consulting Feeds](http://osint.bambenekconsulting.com/feeds/) — Feeds OSINT baseados em algoritmos DGA maliciosos. **Análise:** Nichado, mas útil.
- 🟡 [CI Army](http://cinsscore.com/) ([list](http://cinsscore.com/list/ci-badguys.txt)) — Blocklists de segurança de rede. **Análise:** Funcional.
- 🟡 [Critical Stack - Free Intel Market](https://intel.criticalstack.com) — Agregador de intel gratuito com deduplicação. **Análise:** Útil, mas com desenvolvimento lento.
- 🟡 [Cybercrime tracker](http://cybercrime-tracker.net/) — Rastreador de múltiplos botnets ativos. **Análise:** Fonte útil, mas irregular.
- 🟡 [Fidelis Barncat](https://www.fidelissecurity.com/resources/fidelis-barncat) — Banco de dados extenso de configurações de malware (requer solicitação de acesso). **Análise:** Útil para pesquisadores.
- 🟡 [HoneyDB](https://riskdiscovery.com/honeydb) — Coleta e agregação de dados de sensores honeypot. **Análise:** Comunitário.
- 🟡 [hpfeeds](https://github.com/rep/hpfeeds) — Protocolo de feed de honeypot. **Análise:** Nichado.
- 🟡 [Infosec - CERT-PA lists](https://infosec.cert-pa.it/analyze/statistics.html) — Serviço de blocklist. **Análise:** Recurso italiano.
- 🟡 [malc0de](http://malc0de.com/database/) — Banco de dados pesquisável de incidentes. **Análise:** Histórico, manutenção lenta.
- 🟡 [Malware Domain List](http://www.malwaredomainlist.com/) — Pesquise e compartilhe URLs maliciosas. **Análise:** Projeto histórico, em declínio.
- 🟡 [MetaDefender Threat Intelligence Feed](https://www.opswat.com/developers/threat-intelligence-feed) — Lista dos hashes de arquivos mais consultados no MetaDefender Cloud. **Análise:** Útil.
- 🟡 [OpenIOC](https://www.fireeye.com/services/freeware.html) — Framework para compartilhamento de threat intelligence. **Análise:** Legado, mas ainda referenciado.
- 🟡 [Ransomware overview](https://docs.google.com/spreadsheets/d/1TWS238xacAto-fLKh1n5uTsdijWdCEsGIM0Y0Hvmc5g/pubhtml) — Lista de ransomware com detalhes, detecção e prevenção. **Análise:** Útil, mas depende de curadoria manual.
- 🟡 [SystemLookup](https://www.systemlookup.com/) — Listas com informações sobre componentes de programas legítimos e potencialmente indesejados. **Análise:** Útil para triagem.
- 🟡 [ThreatShare](https://threatshare.io/) — Rastreador de painéis C2. **Análise:** Nichado.
- 🟡 [Zeltser's List](https://zeltser.com/lookup-malicious-websites/) — Ferramentas online gratuitas para pesquisar sites maliciosos. **Análise:** Excelente recurso meta.


---

## Detecção e Classificação

*Antivírus e outras ferramentas de identificação de malware.*

- 🟢 [capa](https://github.com/mandiant/capa) — Detecta capacidades em arquivos executáveis. **Análise:** Ferramenta essencial para triagem rápida. Mantida pela Mandiant/Google.
- 🟢 [ClamAV](https://www.clamav.net/) — Motor antivírus open source. **Análise:** Padrão para detecção open source. Mantido pela Cisco.
- 🟢 [YARA](https://github.com/VirusTotal/yara) — Ferramenta de correspondência de padrões para analistas. **Análise:** Indispensável. Padrão de facto da indústria.
- 🟢 [Loki](https://github.com/Neo23x0/Loki) — Scanner baseado em host para IOCs. **Análise:** Excelente para detecção em endpoints. Mantido por Florian Roth.
- 🟢 [Yara rules generator (yarGen)](https://github.com/Neo23x0/yarGen) — Gera regras YARA com base em um conjunto de amostras de malware. **Análise:** Extremamente útil para criar regras precisas.
- 🟢 [Manalyze](https://github.com/JusticeRage/Manalyze) — Analisador estático para executáveis PE. **Análise:** Robusto e bem mantido.
- 🟢 [PEframe](https://github.com/guelfoweb/peframe) — Análise estática de malware PE e documentos maliciosos do MS Office. **Análise:** Bom para triagem inicial.
- 🟢 [PortEx](https://github.com/katjahahn/PortEx) — Biblioteca Java para analisar arquivos PE com foco em robustez. **Análise:** Excelente para automação.
- 🟢 [Quark-Engine](https://github.com/quark-engine/quark-engine) — Sistema de pontuação de malware Android com foco em obfuscação. **Análise:** Nichado, mas essencial para mobile.
- 🟢 [StringSifter](https://github.com/fireeye/stringsifter) 🤖 — Ferramenta de machine learning que classifica strings automaticamente com base em sua relevância para análise de malware. **Análise:** Extremamente útil para reduzir ruído em análises.
- 🟢 [Detect It Easy (DiE)](https://github.com/horsicq/Detect-It-Easy) — Programa para determinar tipos de arquivos. **Análise:** Essencial para identificar packers e compiladores.
- 🟢 [ExifTool](https://exiftool.org/) — Leia, escreva e edite metadados de arquivos. **Análise:** Clássico e indispensável.
- 🟢 [hashdeep](https://github.com/jessek/hashdeep) — Calcule hashes digest com uma variedade de algoritmos. **Análise:** Útil para triagem em lote.
- 🟢 [ssdeep](https://ssdeep-project.github.io/ssdeep/) — Calcule hashes fuzzy. **Análise:** Útil para agrupamento de amostras similares.
- 🟢 [PE-bear](https://github.com/hasherezade/pe-bear) — Ferramenta de reversing para arquivos PE. **Análise:** Leve e rápida, excelente para triagem.
- 🟢 [PEV](https://github.com/merces/pev) — Kit de ferramentas multiplataforma para trabalhar com arquivos PE. **Análise:** Robusto, mantido pela comunidade.
- 🟢 [AnalyzePE](https://github.com/hiddenillusion/AnalyzePE) — Wrapper para várias ferramentas de relatório em arquivos PE do Windows. **Análise:** Útil para automação.
- 🟡 [Malfunction](https://github.com/Dynetics/Malfunction) — Catalogue e compare malware em nível de função. **Análise:** Ferramenta de pesquisa, mas com desenvolvimento lento.
- 🟡 [MASTIFF](https://github.com/KoreLogicSecurity/mastiff) — Framework de análise estática. **Análise:** Útil, mas manutenção irregular.
- 🟡 [MultiScanner](https://github.com/mitre/multiscanner) — Framework modular de varredura/análise de arquivos. **Análise:** Funcional, mas com desenvolvimento lento.
- 🟡 [nsrllookup](https://github.com/rjhansen/nsrllookup) — Ferramenta para pesquisar hashes na National Software Reference Library do NIST. **Análise:** Nichado.
- 🟡 [packerid](https://github.com/sooshie/packerid) — Alternativa Python multiplataforma ao PEiD. **Análise:** Útil para identificar packers.
- 🟡 [Rootkit Hunter](http://rkhunter.sourceforge.net/) — Detecta rootkits Linux. **Análise:** Clássico, mas com desenvolvimento lento.
- 🟡 [chkrootkit](http://www.chkrootkit.org/) — Detecção local de rootkits Linux. **Análise:** Clássico, ainda funcional.
- 🟡 [Exeinfo PE](http://exeinfo.pe.hu/) — Detector de packers, compressores e ferramentas internas de EXE. **Análise:** Ferramenta clássica, ainda útil.
- 🟡 [TrID](http://mark0.net/soft-trid-e.html) — Identificador de arquivos. **Análise:** Simples e funcional.
- 🟡 [Nauz File Detector (NFD)](https://github.com/horsicq/Nauz-File-Detector) — Detector de linker/compilador/ferramenta para Windows, Linux e MacOS. **Análise:** Nichado, útil.
- 🟡 [Generic File Parser](https://github.com/uppusaikiran/generic-parser) — Parser único para extrair meta-informação, análise estática e detectar macros. **Análise:** Útil, mas com escopo limitado.
- 🟡 [HashCheck](https://github.com/gurnec/HashCheck) — Extensão do shell do Windows para calcular hashes. **Análise:** Conveniente, mas Windows-only.
- 🟡 [fn2yara](https://github.com/cmu-sei/pharos) — Gera assinaturas Yara para funções correspondentes em um programa executável. **Análise:** Nichado, mas poderoso.
- 🟡 [totalhash.py](https://gist.github.com/gleblanc1783/3c8e6b379fa9d646d401b96ab5c7877f) — Script Python para pesquisa fácil no banco de dados TotalHash.cymru.com. **Análise:** Legado, o site pode estar fora do ar.
- 🟡 [Yara Finder](https://github.com/uppusaikiran/yara-finder) — Ferramenta simples para fazer match de arquivos contra várias regras Yara. **Análise:** Simples e funcional.

---

## Scanners Online e Sandboxes

*Scanners multi-AV baseados na web e sandboxes de malware para análise automatizada.*

- 🟢 [any.run](https://app.any.run/) — Sandbox online interativo. **Análise:** Excelente para análise dinâmica interativa. Plano gratuito limitado. Um dos líderes do mercado.
- 🟢 [CAPEv2](https://github.com/kevoreilly/CAPEv2) — 🆕 Sandbox open source, self-hosted, fork do Cuckoo com extração automatizada de configuração e desempacotamento. **Análise:** **Este é o substituto oficial do Cuckoo Sandbox.** Mantido ativamente e recomendado para ambientes self-hosted.
- 🟢 [DRAKVUF](https://github.com/tklengyel/drakvuf) — Sistema de análise dinâmica de malware. **Análise:** Análise em nível de hipervisor. Extremamente poderoso para malware evasivo. Mantido ativamente.
- 🟢 [Hybrid Analysis](https://www.hybrid-analysis.com/) — Ferramenta online de análise de malware, alimentada pelo VxSandbox. **Análise:** Excelente plano gratuito, relatórios detalhados.
- 🟢 [Joe Sandbox](https://www.joesecurity.org) — Análise profunda de malware. **Análise:** Um dos sandboxes comerciais mais completos. Caro, mas poderoso.
- 🟢 [VirusTotal](https://www.virustotal.com/) — Análise online gratuita de amostras de malware e URLs. **Análise:** Indispensável. Agora com análise por IA (Code Insight).
- 🟢 [filescan.io](https://www.filescan.io/) — Análise estática de malware, emulação de VBA/Powershell/VBS/JS. **Análise:** Bom complemento ao VirusTotal.
- 🟢 [Intezer](https://analyze.intezer.com) — Detecta, analisa e categoriza malware identificando reuso e similaridades de código. **Análise:** Abordagem única baseada em "DNA" de código. Excelente para atribuição.
- 🟢 [NetworkTotal](https://www.networktotal.com/index.html) — Serviço que analisa arquivos pcap usando Suricata configurado com EmergingThreats Pro. **Análise:** Nichado, mas útil para análise de tráfego.
- 🟢 [PacketTotal](https://packettotal.com/) — Motor online para analisar arquivos .pcap e visualizar o tráfego de rede. **Análise:** Muito útil para análise de tráfego de malware.
- 🟢 [sandboxapi](https://github.com/InQuest/python-sandboxapi) — Biblioteca Python para construir integrações com vários sandboxes de malware. **Análise:** Excelente para automação.
- 🟢 [Noriben](https://github.com/Rurik/Noriben) — Usa Sysinternals Procmon para coletar informações sobre malware em ambiente sandbox. **Análise:** Útil para análise comportamental manual.
- 🟢 [ProcDot](https://www.procdot.com) — Kit gráfico de análise de malware. **Análise:** Visualização de logs de Procmon. Excelente para entender cadeias de execução.
- 🟢 [Malware config](https://malwareconfig.com/) — Extraia, decodifique e exiba online as configurações de malwares comuns. **Análise:** Extremamente útil para análise rápida de configs.
- 🟢 [MetaDefender Cloud](https://metadefender.opswat.com/) — Escaneie arquivo, hash, IP, URL ou domínio gratuitamente. **Análise:** Alternativa ao VirusTotal.
- 🟢 [HaboMalHunter](https://github.com/Tencent/HaboMalHunter) — Ferramenta automatizada de análise de malware para arquivos ELF Linux. **Análise:** Nichado, útil para malware Linux.
- 🟢 [Limon](https://github.com/monnappa22/Limon) — Sandbox para análise de malware Linux. **Análise:** Nichado.
- 🟢 [detux](https://github.com/detuxsandbox/detux/) — Sandbox para análise de tráfego de malwares Linux e captura de IOCs. **Análise:** Nichado.
- 🟢 [IRMA](https://github.com/quarkslab/irma) — Plataforma de análise assíncrona e personalizável para arquivos suspeitos. **Análise:** Excelente para self-hosted.
- 🟢 [Visualize_Logs](https://github.com/keithjjones/visualize_logs) — Biblioteca open source de visualização e ferramentas de linha de comando para logs. **Análise:** Útil para análise de logs de sandbox.
- 🟡 [anlyz.io](https://sandbox.anlyz.io/) — Sandbox online. **Análise:** Menos conhecido, funcional.
- 🟡 [AndroTotal](https://andrototal.org/) — Análise online gratuita de APKs contra múltiplos antivírus móveis. **Análise:** Nichado, útil para Android.
- 🟡 [BoomBox](https://github.com/nbeede/BoomBox) — Implantação automática de laboratório de malware Cuckoo Sandbox usando Packer e Vagrant. **Análise:** Legado, mas útil para configurar labs.
- 🟡 [cuckoo-modified](https://github.com/brad-accuvant/cuckoo-modified) — Versão modificada do Cuckoo Sandbox. **Análise:** Descontinuado em favor do CAPEv2.
- 🟡 [cuckoo-modified-api](https://github.com/keithjjones/cuckoo-modified-api) — API Python para controlar um sandbox cuckoo-modified. **Análise:** Legado.
- 🟡 [DeepViz](https://www.deepviz.com/) — Analisador de arquivos multi-formato com classificação por machine learning. **Análise:** Interessante, mas com desenvolvimento lento.
- 🟡 [firmware.re](http://firmware.re/) — Descompacta, escaneia e analisa quase qualquer pacote de firmware. **Análise:** Nichado, mas muito útil para IoT.
- 🟡 [Jotti](https://virusscan.jotti.org/en) — Scanner multi-AV online gratuito. **Análise:** Alternativa ao VirusTotal, mas com menos engines.
- 🟡 [Malheur](https://github.com/rieck/malheur) — Análise automática de comportamento de malware em sandbox. **Análise:** Ferramenta de pesquisa, nichada.
- 🟡 [malice.io](https://github.com/maliceio/malice) — Framework de análise de malware massivamente escalável. **Análise:** Interessante, mas com desenvolvimento lento.
- 🟡 [malsub](https://github.com/diogo-fernan/malsub) — Framework de API RESTful em Python para serviços online de análise de malware e URL. **Análise:** Útil para automação.
- 🟡 [MalwareAnalyser.io](https://malwareanalyser.io/) — Analisador estático online com detecção heurística baseada em data mining e machine learning. **Análise:** Interessante, mas menos conhecido.
- 🟡 [PDF Examiner](http://www.pdfexaminer.com/) — Analise arquivos PDF suspeitos. **Análise:** Nichado.
- 🟡 [Recomposer](https://github.com/secretsquirrel/recomposer) — Script auxiliar para upload seguro de binários para sites de sandbox. **Análise:** Útil.
- 🟡 [SEE](https://github.com/F-Secure/see) — Framework para construir automação de testes em ambientes seguros. **Análise:** Nichado.
- 🟡 [SEKOIA Dropper Analysis](https://malware.sekoia.fr/) — Análise online de droppers (Js, VBScript, Microsoft Office, PDF). **Análise:** Gratuito e útil.

---

## Análise de Domínio

*Inspecione domínios e endereços IP.*

- 🟢 [AbuseIPDB](https://www.abuseipdb.com/) — Projeto dedicado a ajudar a combater a propagação de hackers, spammers e atividades abusivas na internet. **Análise:** API robusta, banco de dados comunitário.
- 🟢 [urlscan.io](https://urlscan.io/) — Scanner de URL gratuito e informações de domínio. **Análise:** Indispensável para análise de URLs suspeitas.
- 🟢 [URLhaus](https://urlhaus.abuse.ch/) — Projeto da abuse.ch para compartilhar URLs maliciosas usadas para distribuição de malware. **Análise:** Recurso essencial.
- 🟢 [SecurityTrails](https://securitytrails.com/) — WHOIS histórico e atual, registros DNS históricos e atuais, domínios similares, informações de certificados e outros. **Análise:** Excelente para investigações de infraestrutura.
- 🟢 [dnstwist](https://github.com/elceef/dnstwist) — Motor de permutação de nomes de domínio para detectar typosquatting, phishing e espionagem corporativa. **Análise:** Muito útil para detecção de domínios falsos.
- 🟢 [Talos Intelligence](https://talosintelligence.com/) — Pesquise por IP, domínio ou proprietário de rede. **Análise:** Recurso da Cisco, muito confiável.
- 🟢 [Sucuri SiteCheck](https://sitecheck.sucuri.net/) — Scanner gratuito de malware e segurança de sites. **Análise:** Útil para verificação rápida.
- 🟢 [urlquery.net](http://urlquery.net/) — Scanner de URL gratuito. **Análise:** Funcional.
- 🟢 [Machinae](https://github.com/hurricanelabs/machinae) — Ferramenta OSINT para coletar informações sobre URLs, IPs ou hashes. **Análise:** Útil para automação de investigações.
- 🟢 [TekDefense Automater](http://www.tekdefense.com/automater/) — Ferramenta OSINT para coletar informações sobre URLs, IPs ou hashes. **Análise:** Similar ao Machinae, útil.
- 🟢 [IPinfo](https://github.com/hiddenillusion/IPinfo) — Colete informações sobre um IP ou domínio pesquisando recursos online. **Análise:** Script útil.
- 🟢 [mailchecker](https://github.com/FGRibreau/mailchecker) — Biblioteca de detecção de e-mail temporário em várias linguagens. **Análise:** Nichado, mas útil.
- 🟢 [SpamHaus](https://www.spamhaus.org/lookup/) — Blocklist baseada em domínios e IPs. **Análise:** Clássico e confiável.
- 🟢 [PhishStats](https://phishstats.info/) — Estatísticas de phishing com busca por IP, domínio e título do site. **Análise:** Útil para investigações de phishing.
- 🟡 [badips.com](https://www.badips.com/) — Serviço comunitário de blacklist de IP. **Análise:** Funcional, mas comunitário.
- 🟡 [boomerang](https://github.com/EmersonElectricCo/boomerang) — Ferramenta projetada para captura consistente e segura de recursos web fora da rede. **Análise:** Nichado.
- 🟡 [Desenmascara.me](http://desenmascara.me) — Ferramenta de um clique para recuperar o máximo de metadados possível de um site. **Análise:** Útil, mas com desenvolvimento lento.
- 🟡 [Dig](https://networking.ringofsaturn.com/) — Ferramenta online gratuita de dig e outras ferramentas de rede. **Análise:** Conveniente.
- 🟡 [MaltegoVT](https://github.com/michael-yip/MaltegoVT) — Transformação Maltego para a API do VirusTotal. **Análise:** Útil para usuários do Maltego.
- 🟡 [Multi rbl](http://multirbl.valli.org/) — Múltiplas blacklists DNS e verificação reversa de DNS. **Análise:** Útil.
- 🟡 [NormShield Services](https://services.normshield.com/) — Serviços de API gratuitos para detectar possíveis domínios de phishing, IPs em blacklist e contas comprometidas. **Análise:** Funcional.
- 🟡 [SpamCop](https://www.spamcop.net/bl.shtml) — Lista de bloqueio de spam baseada em IP. **Análise:** Clássico.
- 🟡 [Whois](https://whois.domaintools.com/) — Pesquisa whois online gratuita da DomainTools. **Análise:** Conveniente.
- 🟡 [ZScalar Zulu](https://zulu.zscaler.com/#) — Analisador de risco de URL. **Análise:** Útil.

> **Removidos:** `Cymon` (descontinuado). `Spyse` (serviço descontinuado).

---

## Malware de Navegador

*Analise URLs maliciosas. Veja também as seções de [análise de domínio](#análise-de-domínio) e [documentos e shellcode](#documentos-e-shellcode).*

- 🟢 [JSDetox](http://www.relentless-coding.com/projects/jsdetox/) — Ferramenta de análise de malware JavaScript. **Análise:** Útil para análise de JavaScript malicioso.
- 🟢 [box-js](https://github.com/CapacitorSet/box-js) — Ferramenta para estudar malware JavaScript, com suporte a JScript/WScript e emulação ActiveX. **Análise:** Excelente para análise de scripts maliciosos.
- 🟢 [Krakatau](https://github.com/Storyyeller/Krakatau) — Descompilador, montador e desmontador Java. **Análise:** Útil para análise de malware Java.
- 🟢 [Java Decompiler](http://jd.benow.ca/) — Descompile e inspecione aplicativos Java. **Análise:** Clássico.
- 🟢 [Bytecode Viewer](https://github.com/Konloch/bytecode-viewer) — Combina múltiplos visualizadores e descompiladores de bytecode Java em uma ferramenta, incluindo suporte a APK/DEX. **Análise:** Excelente para análise de Android e Java.
- 🟡 [Firebug](https://getfirebug.com/) — Extensão Firefox para desenvolvimento web. **Análise:** Legado, substituído pelas DevTools.
- 🟡 [Java IDX Parser](https://github.com/Rurik/Java_IDX_Parser/) — Analisa arquivos de cache Java IDX. **Análise:** Nichado.
- 🟡 [jsunpack-n](https://github.com/urule99/jsunpack-n) — Desempacotador JavaScript que emula funcionalidades do navegador. **Análise:** Útil, mas com desenvolvimento lento.
- 🟡 [Malzilla](http://malzilla.sourceforge.net/) — Analise páginas web maliciosas. **Análise:** Clássico.
- 🟡 [RABCDAsm](https://github.com/CyberShadow/RABCDAsm) — Desmontador robusto de bytecode ActionScript. **Análise:** Nichado para Flash.
- 🟡 [SWF Investigator](https://labs.adobe.com/technologies/swfinvestigator/) — Análise estática e dinâmica de aplicativos SWF. **Análise:** Legado Flash.
- 🟡 [swftools](http://www.swftools.org/) — Ferramentas para trabalhar com arquivos Adobe Flash. **Análise:** Legado Flash.
- 🟡 [xxxswf](http://hooked-on-mnemonics.blogspot.com/2011/12/xxxswfpy.html) — Script Python para analisar arquivos Flash. **Análise:** Legado Flash.

---

## Documentos e Shellcode

*Analise JavaScript malicioso e shellcode de PDFs e documentos do Office. Veja também a seção de [malware de navegador](#malware-de-navegador).*

- 🟢 [olevba](https://github.com/decalage2/oletools) — Script para analisar documentos OLE e OpenXML e extrair informações úteis. **Análise:** Parte do oletools. Indispensável para análise de maldocs.
- 🟢 [peepdf](https://github.com/jesparza/peepdf) — Ferramenta Python para explorar PDFs possivelmente maliciosos. **Análise:** Ferramenta de referência para análise de PDF.
- 🟢 [AnalyzePDF](https://github.com/hiddenillusion/AnalyzePDF) — Ferramenta para analisar PDFs e tentar determinar se são maliciosos. **Análise:** Útil para triagem.
- 🟢 [QuickSand](https://www.quicksand.io/) — Framework C compacto para analisar documentos suspeitos. **Análise:** Poderoso para análise de documentos.
- 🟢 [diStorm](http://www.ragestorm.net/distorm/) — Desmontador para analisar shellcode malicioso. **Análise:** Clássico.
- 🟢 [libemu](http://libemu.carnivore.it/) — Biblioteca e ferramentas para emulação de shellcode x86. **Análise:** Útil para análise de shellcode.
- 🟢 [Spidermonkey](https://developer.mozilla.org/en-US/docs/Mozilla/Projects/SpiderMonkey) — Motor JavaScript da Mozilla, para depurar JS malicioso. **Análise:** Útil, mas pesado.
- 🟢 [InQuest Deep File Inspection](https://labs.inquest.net/dfi) — Upload de iscas de malware comuns para inspeção profunda de arquivos e análise heurística. **Análise:** Excelente recurso gratuito.
- 🟢 [PDF Tools](https://blog.didierstevens.com/programs/pdf-tools/) — pdfid, pdf-parser e mais do Didier Stevens. **Análise:** Conjunto clássico de ferramentas para análise de PDF.
- 🟢 [PDF X-Ray Lite](https://github.com/9b/pdfxray_lite) — Ferramenta de análise de PDF, versão sem backend do PDF X-RAY. **Análise:** Útil.
- 🟡 [OfficeMalScanner](http://www.reconstructer.org/code.html) — Procure por traços maliciosos em documentos do MS Office. **Análise:** Funcional, mas com desenvolvimento lento.
- 🟡 [malpdfobj](https://github.com/9b/malpdfobj) — Desconstrua PDFs maliciosos em uma representação JSON. **Análise:** Nichado.
- 🟡 [Origami PDF](https://code.google.com/archive/p/origami-pdf) — Ferramenta para analisar PDFs maliciosos. **Análise:** Legado, hospedado no Google Code Archive.
- 🟡 [JS Beautifier](http://jsbeautifier.org/) — Desempacotamento e desobfuscação de JavaScript. **Análise:** Útil para análise de scripts ofuscados.

---

## File Carving

*Para extrair arquivos de dentro de imagens de disco e memória.*

- 🟢 [bulk_extractor](https://github.com/simsong/bulk_extractor) — Ferramenta rápida de file carving. **Análise:** Excelente para extração de dados forenses.
- 🟢 [Scalpel](https://github.com/sleuthkit/scalpel) — Outra ferramenta de data carving. **Análise:** Robusta e bem mantida.
- 🟢 [Foremost](http://foremost.sourceforge.net/) — Ferramenta de file carving projetada pela Força Aérea dos EUA. **Análise:** Clássico.
- 🟢 [hachoir3](https://github.com/vstinner/hachoir3) — Biblioteca Python para visualizar e editar um fluxo binário campo por campo. **Análise:** Muito útil para análise de formatos de arquivo.
- 🟢 [EVTXtract](https://github.com/williballenthin/EVTXtract) — Extraia arquivos de log de eventos do Windows de dados binários brutos. **Análise:** Nichado, mas útil.
- 🟡 [SFlock](https://github.com/jbremer/sflock) — Extração/desempacotamento de arquivos aninhados (usado no Cuckoo Sandbox). **Análise:** Legado, mas funcional.

---

## Desobfuscação

*Reverta XOR e outros métodos de ofuscação de código.*

- 🟢 [FLOSS](https://github.com/mandiant/flare-floss) 🤖 — O FireEye Labs Obfuscated String Solver usa técnicas avançadas de análise estática para automaticamente desobfuscar strings de binários de malware. **Análise:** **Ferramenta indispensável.** Extremamente poderosa para extrair strings de binários ofuscados.
- 🟢 [xortool](https://github.com/hellman/xortool) — Adivinhe o comprimento da chave XOR, bem como a própria chave. **Análise:** Essencial para análise de XOR.
- 🟢 [de4dot](https://github.com/0xd4d/de4dot) — Desobfuscador e desempacotador .NET. **Análise:** Clássico e ainda muito utilizado.
- 🟢 [uncompyle6](https://github.com/rocky/python-uncompyle6/) — Descompilador de bytecode Python multi-versão. **Análise:** Excelente para análise de malware Python.
- 🟢 [PyInstaller Extractor](https://github.com/extremecoders-re/pyinstxtractor) — Script Python para extrair o conteúdo de um executável Windows gerado pelo PyInstaller. **Análise:** Essencial para malware empacotado com PyInstaller.
- 🟢 [NoMoreXOR](https://github.com/hiddenillusion/NoMoreXOR) — Adivinhe uma chave XOR de 256 bytes usando análise de frequência. **Análise:** Útil para XOR simples.
- 🟢 [unxor](https://github.com/tomchop/unxor/) — Adivinhe chaves XOR usando ataques de texto simples conhecido. **Análise:** Útil.
- 🟢 [XORSearch & XORStrings](https://blog.didierstevens.com/programs/xorsearch/) — Programas do Didier Stevens para encontrar dados XORed. **Análise:** Clássico.
- 🟢 [PackerAttacker](https://github.com/BromiumLabs/PackerAttacker) — Extrator genérico de código oculto para malware Windows. **Análise:** Útil para desempacotamento.
- 🟢 [un{i}packer](https://github.com/unipacker/unipacker) — Desempacotador automático e independente de plataforma para binários Windows baseado em emulação. **Análise:** Poderoso.
- 🟢 [VirtualDeobfuscator](https://github.com/jnraber/VirtualDeobfuscator) — Ferramenta de engenharia reversa para wrappers de virtualização. **Análise:** Nichado, mas poderoso.
- 🟢 [Balbuzard](https://bitbucket.org/decalage/balbuzard/wiki/Home) — Ferramenta de análise de malware para reverter ofuscação (XOR, ROL, etc). **Análise:** Útil.
- 🟡 [ex_pe_xor & iheartxor](http://hooked-on-mnemonics.blogspot.com/2014/04/expexorpy.html) — Duas ferramentas de Alexander Hanel para trabalhar com arquivos codificados com XOR de byte único. **Análise:** Legado, mas funcional.
- 🟡 [unpacker](https://github.com/malwaremusings/unpacker/) — Desempacotador automatizado de malware para Windows baseado em WinAppDbg. **Análise:** Útil, mas com desenvolvimento lento.
- 🟡 [XORBruteForcer](http://eternal-todo.com/var/scripts/xorbruteforcer) — Script Python para forçar chaves XOR de byte único. **Análise:** Simples.

---

## Debug e Engenharia Reversa

*Desmontadores, depuradores e outras ferramentas de análise estática e dinâmica.*

- 🟢 [Ghidra](https://github.com/NationalSecurityAgency/ghidra) — Framework de engenharia reversa de software (SRE) criado e mantido pela National Security Agency. **Análise:** **Padrão open source.** Gratuito, poderoso e com decompilador de alta qualidade. Essencial.
- 🟢 [x64dbg](https://github.com/x64dbg/x64dbg) — Depurador open source x64/x32 para Windows. **Análise:** **O melhor depurador gratuito para Windows.** Essencial para análise dinâmica.
- 🟢 [IDA Pro](https://hex-rays.com/ida-pro/) — Desmontador e depurador Windows, com versão de avaliação gratuita. **Análise:** Padrão comercial da indústria. Caro, mas extremamente poderoso.
- 🟢 [Binary Ninja](https://binary.ninja/) — Plataforma de engenharia reversa alternativa ao IDA. **Análise:** Excelente alternativa comercial com API moderna.
- 🟢 [Radare2](https://github.com/radareorg/radare2) — Framework de engenharia reversa com suporte a depurador. **Análise:** Poderoso, mas com curva de aprendizado íngreme.
- 🟢 [Cutter](https://github.com/radareorg/cutter) — GUI para Radare2. **Análise:** Torna o Radare2 mais acessível.
- 🟢 [Capstone](https://github.com/capstone-engine/capstone) — Framework de desmontagem para análise binária e engenharia reversa. **Análise:** Biblioteca essencial para ferramentas de análise.
- 🟢 [angr](https://github.com/angr/angr) — Framework de análise binária agnóstico de plataforma. **Análise:** Poderoso para análise simbólica e automação.
- 🟢 [Qiling Framework](https://github.com/qilingframework/qiling) — Framework de emulação e sandboxing multiplataforma com instrumentos para análise binária. **Análise:** Excelente para análise de malware multiplataforma.
- 🟢 [GEF](https://github.com/hugsy/gef) — GDB Enhanced Features para exploradores e engenheiros reversos. **Análise:** Essencial para quem usa GDB.
- 🟢 [PEDA](https://github.com/longld/peda) — Python Exploit Development Assistance para GDB. **Análise:** Alternativa ao GEF.
- 🟢 [RetDec](https://github.com/avast/retdec) — Descompilador de código de máquina retargetável. **Análise:** Excelente ferramenta gratuita.
- 🟢 [pestudio](https://www.winitor.com/) — Análise estática de executáveis Windows. **Análise:** **Ferramenta essencial** para triagem de PE. Extremamente detalhada.
- 🟢 [Process Monitor](https://learn.microsoft.com/en-us/sysinternals/downloads/procmon) — Ferramenta de monitoramento avançado para programas Windows. **Análise:** Indispensável para análise dinâmica.
- 🟢 [Process Explorer](https://learn.microsoft.com/en-us/sysinternals/downloads/process-explorer) — Gerenciador de tarefas avançado para Windows. **Análise:** Essencial.
- 🟢 [Process Hacker](https://processhacker.sourceforge.io/) — Ferramenta que monitora recursos do sistema. **Análise:** Excelente alternativa ao Process Explorer.
- 🟢 [System Informer](https://systeminformer.sourceforge.io/) — 🆕 Ferramenta avançada de monitoramento de sistema, antigo Process Hacker. **Análise:** **Recomendado.** Mais ativo que o Process Hacker original.
- 🟢 [Autoruns](https://learn.microsoft.com/en-us/sysinternals/downloads/autoruns) — 🆕 Mostra quais programas estão configurados para iniciar durante o boot. **Análise:** Essencial para análise de persistência.
- 🟢 [ScyllaHide](https://github.com/x64dbg/ScyllaHide) — Biblioteca anti-anti-debug e plugin para OllyDbg, x64dbg, IDA Pro e TitanEngine. **Análise:** Útil para contornar técnicas anti-debug.
- 🟢 [Scylla Imports Reconstructor](https://github.com/NtQuery/Scylla) — Encontre e corrija o IAT de um malware PE32 desempacotado. **Análise:** Útil para reconstrução de imports.
- 🟢 [LIEF](https://lief-project.github.io/) — Biblioteca multiplataforma para analisar, modificar e abstrair formatos ELF, PE e MachO. **Análise:** Excelente para automação de análise de formato.
- 🟢 [Kaitai Struct](https://kaitai.io/) — DSL para formatos de arquivo / protocolos de rede / estruturas de dados. **Análise:** Poderoso para engenharia reversa de formatos.
- 🟢 [Fibratus](https://github.com/rabbitstack/fibratus) — Ferramenta para exploração e rastreamento do kernel do Windows. **Análise:** Útil para análise de rootkits.
- 🟢 [Triton](https://github.com/JonathanSalwan/Triton) — Framework de análise binária dinâmica (DBA). **Análise:** Poderoso para análise simbólica.
- 🟢 [PANDA](https://github.com/panda-re/panda) — Plataforma para Análise Dinâmica Neutra em Arquitetura. **Análise:** Útil para análise de malware em larga escala.
- 🟢 [PyREBox](https://github.com/Cisco-Talos/pyrebox) — Sandbox de engenharia reversa scriptável em Python. **Análise:** Excelente para automação. Mantido pela Cisco Talos.
- 🟢 [ROPMEMU](https://github.com/Cisco-Talos/ROPMEMU) — Framework para analisar, dissecar e descompilar ataques complexos de reuso de código. **Análise:** Nichado, mas poderoso.
- 🟢 [dnSpy](https://github.com/dnSpyEx/dnSpy) — Editor, descompilador e depurador de assembly .NET. **Análise:** **Essencial para malware .NET.** A versão original foi descontinuada, use o fork dnSpyEx.
- 🟢 [ILSpy](https://github.com/icsharpcode/ILSpy) — Navegador e descompilador de assembly .NET open source. **Análise:** Alternativa ao dnSpy.
- 🟢 [dotPeek](https://www.jetbrains.com/decompiler/) — Descompilador .NET e navegador de assembly gratuito da JetBrains. **Análise:** Excelente para análise de .NET.
- 🟢 [de4dot](https://github.com/0xd4d/de4dot) — Desobfuscador .NET. **Análise:** Essencial para malware .NET ofuscado.
- 🟢 [Binwalk](https://github.com/ReFirmLabs/binwalk) — Ferramenta de análise de firmware. **Análise:** Essencial para análise de firmware IoT.
- 🟢 [GDB](https://www.sourceware.org/gdb/) — O depurador GNU. **Análise:** Clássico e indispensável para Linux.
- 🟢 [strace](https://strace.io/) — Análise dinâmica para executáveis Linux. **Análise:** Essencial para análise de malware Linux.
- 🟢 [ltrace](http://ltrace.org/) — Análise dinâmica para executáveis Linux. **Análise:** Complementar ao strace.
- 🟢 [objdump](https://en.wikipedia.org/wiki/Objdump) — Parte do GNU binutils, para análise estática de binários Linux. **Análise:** Clássico.
- 🟢 [PSTools](https://learn.microsoft.com/en-us/sysinternals/downloads/pstools) — Ferramentas de linha de comando do Windows para gerenciar e investigar sistemas ativos. **Análise:** Kit essencial da Sysinternals.
- 🟢 [FPort](https://www.mcafee.com/us/downloads/free-tools/fport.aspx) — Relata portas TCP/IP e UDP abertas em um sistema ativo. **Análise:** Útil, mas antigo.
- 🟡 [OllyDbg](http://www.ollydbg.de/) — Depurador em nível de assembly para executáveis Windows. **Análise:** Legado, mas ainda usado. Substituído pelo x64dbg.
- 🟡 [OllyDumpEx](https://low-priority.appspot.com/ollydumpex/) — Plugin para OllyDbg, Immunity Debugger, IDA Pro, WinDbg e x64dbg. **Análise:** Legado.
- 🟡 [Immunity Debugger](http://debugger.immunityinc.com/) — Depurador para análise de malware com API Python. **Análise:** Legado, substituído pelo x64dbg.
- 🟡 [Evan's Debugger (EDB)](http://codef00.com/projects#debugger) — Depurador modular com GUI Qt. **Análise:** Funcional, mas com desenvolvimento lento.
- 🟡 [hackers-grep](https://github.com/codypierce/hackers-grep) — Utilitário para pesquisar strings em executáveis PE. **Análise:** Útil.
- 🟡 [IDR](https://github.com/crypto2011/IDR) — Reconstructor Delphi Interativo. **Análise:** Nichado para malware Delphi.
- 🟡 [codebro](https://github.com/hugsy/codebro) — Navegador de código web usando clang. **Análise:** Legado.
- 🟡 [plasma](https://github.com/plasma-disassembler/plasma) — Desmontador interativo para x86/ARM/MIPS. **Análise:** Funcional, mas com desenvolvimento lento.
- 🟡 [PPEE (puppy)](https://www.mzrst.com/) — Explorador profissional de arquivos PE para reversores. **Análise:** Útil, mas Windows-only.
- 🟡 [Hopper](https://www.hopperapp.com/) — O desmontador macOS e Linux. **Análise:** Comercial, mas acessível.
- 🟡 [Udis86](https://github.com/vmt/udis86) — Biblioteca e ferramenta de desmontagem para x86 e x86_64. **Análise:** Funcional, mas com desenvolvimento lento.
- 🟡 [Vivisect](https://github.com/vivisect/vivisect) — Ferramenta Python para análise de malware. **Análise:** Poderoso, mas com desenvolvimento lento.
- 🟡 [bamfdetect](https://github.com/bwall/bamfdetect) — Identifica e extrai informações de bots e outros malwares. **Análise:** Útil para análise de bots.
- 🟡 [BAP](https://github.com/BinaryAnalysisPlatform/bap) — Framework de análise binária multiplataforma e open source. **Análise:** Poderoso, mas com desenvolvimento mais lento.
- 🟡 [BARF](https://github.com/programa-stic/barf-project) — Framework de análise binária e engenharia reversa multiplataforma. **Análise:** Funcional.
- 🟡 [binnavi](https://github.com/google/binnavi) — IDE de análise binária para engenharia reversa baseada em visualização de grafos. **Análise:** Descontinuado pelo Google, mas ainda funcional.
- 🟡 [DECAF (Dynamic Executable Code Analysis Framework)](https://github.com/sycurelab/DECAF) — Plataforma de análise binária baseada em QEMU. **Análise:** Nichado.
- 🟡 [QKD](https://github.com/ispras/qemu/releases/) — QEMU com servidor WinDbg embutido para depuração furtiva. **Análise:** Nichado.
- 🟡 [WinDbg](https://learn.microsoft.com/en-us/windows-hardware/drivers/debugger/) — Depurador multifuncional para Windows. **Análise:** Essencial para análise de kernel e drivers.
- 🟡 [mac-a-mal](https://github.com/phdphuc/mac-a-mal) — Framework automatizado para caça de malware Mac. **Análise:** Nichado, útil para macOS.
- 🟡 [BluePill](https://github.com/season-lab/bluepill) — Framework para executar e depurar malware evasivo e executáveis protegidos. **Análise:** Nichado.
- 🟡 [Pharos](https://github.com/cmu-sei/pharos) — Framework de análise binária do SEI da CMU. **Análise:** Pesquisa.
- 🟡 [Fibratus](https://github.com/rabbitstack/fibratus) — Ferramenta para exploração e rastreamento do kernel do Windows. **Análise:** Funcional.

---

## Rede

*Analise interações de rede.*

- 🟢 [Wireshark](https://www.wireshark.org/) — A ferramenta de análise de tráfego de rede. **Análise:** Indispensável. Padrão absoluto.
- 🟢 [Zeek](https://zeek.org/) — 🆕 (antigo Bro) Analisador de protocolo que opera em escala incrível. **Análise:** Essencial para monitoramento de rede em larga escala.
- 🟢 [Suricata](https://suricata.io/) — 🆕 Motor IDS/IPS/NSM de alto desempenho. **Análise:** Padrão open source para detecção de intrusão em rede.
- 🟢 [mitmproxy](https://mitmproxy.org/) — Intercepte tráfego de rede em tempo real. **Análise:** Excelente para análise de tráfego HTTP/HTTPS.
- 🟢 [Fiddler](https://www.telerik.com/fiddler) — Proxy web de interceptação projetado para "depuração web". **Análise:** Clássico, ainda útil.
- 🟢 [FakeNet-NG](https://github.com/mandiant/flare-fakenet-ng) — Ferramenta de análise dinâmica de rede de próxima geração. **Análise:** **Essencial para análise de malware.** Simula serviços de rede.
- 🟢 [INetSim](https://www.inetsim.org/) — Emulação de serviços de rede. **Análise:** Útil para construir um laboratório de malware.
- 🟢 [NetworkMiner](https://www.netresec.com/?page=NetworkMiner) — Ferramenta de análise forense de rede. **Análise:** Excelente para extração de artefatos de PCAP.
- 🟢 [CapTipper](https://github.com/omriher/CapTipper) — Explorador de tráfego HTTP malicioso. **Análise:** Útil para análise de tráfego HTTP.
- 🟢 [Maltrail](https://github.com/stamparm/maltrail) — Sistema de detecção de tráfego malicioso. **Análise:** Útil para monitoramento.
- 🟢 [Malcolm](https://github.com/idaholab/Malcolm) — Conjunto de ferramentas de análise de tráfego de rede para PCAP e logs Zeek. **Análise:** Excelente para análise de rede em larga escala.
- 🟢 [Laika BOSS](https://github.com/lmco/laikaboss) — Sistema de análise de malware e detecção de intrusão centrado em arquivos. **Análise:** Poderoso para análise de objetos em tráfego de rede.
- 🟢 [HTTPReplay](https://github.com/jbremer/httpreplay) — Biblioteca para analisar e ler arquivos PCAP, incluindo streams TLS. **Análise:** Útil para análise de tráfego criptografado.
- 🟢 [PcapViz](https://github.com/mateuszk87/PcapViz) — Visualizador de topologia de rede e tráfego. **Análise:** Útil para visualização.
- 🟢 [CloudShark](https://www.cloudshark.org) — Ferramenta web para análise de pacotes e detecção de tráfego de malware. **Análise:** Conveniente.
- 🟢 [ngrep](https://github.com/jpr5/ngrep) — Pesquise através do tráfego de rede como grep. **Análise:** Clássico.
- 🟢 [tcpick](http://tcpick.sourceforge.net/) — Rastreie e remonte streams TCP do tráfego de rede. **Análise:** Útil.
- 🟢 [tcpxtract](http://tcpxtract.sourceforge.net/) — Extraia arquivos do tráfego de rede. **Análise:** Útil.
- 🟢 [Tcpdump](https://www.tcpdump.org/) — Colete tráfego de rede. **Análise:** Indispensável.
- 🟢 [Haka](https://github.com/haka-security/haka) — Linguagem de segurança open source para descrever protocolos e aplicar políticas de segurança. **Análise:** Nichado, mas poderoso.
- 🟢 [chopshop](https://github.com/MITRECND/chopshop) — Framework de análise e decodificação de protocolos. **Análise:** Útil para análise de protocolos.
- 🟢 [Python ICAP Yara](https://github.com/RamadhanAmizudin/python-icap-yara) — Servidor ICAP com scanner YARA para URL ou conteúdo. **Análise:** Nichado.
- 🟢 [Squidmagic](https://github.com/ch3k1/squidmagic) — Ferramenta para analisar tráfego de rede web e detectar servidores C&C. **Análise:** Útil.
- 🟡 [BroYara](https://github.com/hempnall/broyara) — Use regras Yara do Bro. **Análise:** Legado, agora integrado ao Zeek.
- 🟡 [Hale](https://github.com/pjlantz/Hale) — Monitor de C&C de botnet. **Análise:** Nichado, mas funcional.
- 🟡 [Malcom](https://github.com/tomchop/malcom) — Analisador de comunicações de malware. **Análise:** Funcional, mas com desenvolvimento lento.
- 🟡 [Moloch](https://github.com/aol/moloch) — Sistema de captura, indexação e banco de dados de tráfego IPv4. **Análise:** Poderoso, mas a AOL descontinuou o suporte. Comunidade mantém.


---

## Forense de Memória

*Ferramentas para dissecar malware em imagens de memória ou sistemas em execução.*

- 🟢 [Volatility 3](https://github.com/volatilityfoundation/volatility3) — **A versão oficial e suportada.** Volatility 2 foi depreciado em 2025. Framework avançado de forense de memória. **Análise:** **Indispensável.** Padrão absoluto para forense de memória. Suporta Windows XP-11, Linux e macOS.
- 🟢 [evolve](https://github.com/JamesHabben/evolve) — Interface web para o framework Volatility. **Análise:** Útil para quem prefere GUI.
- 🟢 [VolUtility](https://github.com/kevthehermit/VolUtility) — Interface web para o framework Volatility. **Análise:** Alternativa ao evolve.
- 🟢 [DAMM](https://github.com/504ensicsLabs/DAMM) — Análise Diferencial de Malware em Memória, construída sobre Volatility. **Análise:** Muito útil para comparar memória antes/depois da execução de malware.
- 🟢 [VolDiff](https://github.com/aim4r/VolDiff) — Execute Volatility em imagens de memória antes e depois da execução de malware e relate mudanças. **Análise:** Essencial para análise diferencial.
- 🟢 [Muninn](https://github.com/ytisf/muninn) — Script para automatizar partes da análise usando Volatility. **Análise:** Útil para automação.
- 🟢 [Orochi](https://github.com/LDO-CERT/orochi) — Framework open source para análise colaborativa de despejos de memória forense. **Análise:** Excelente para trabalho em equipe.
- 🟢 [WinDbg](https://learn.microsoft.com/en-us/windows-hardware/drivers/debugger/) — Inspeção de memória ao vivo e depuração de kernel para sistemas Windows. **Análise:** Essencial para análise ao vivo.
- 🟢 [TotalRecall](https://github.com/sketchymoose/TotalRecall) — Script baseado em Volatility para automatizar várias tarefas de análise de malware. **Análise:** Útil para automação.
- 🟢 [FindAES](https://sourceforge.net/projects/findaes/) — Encontre chaves de criptografia AES na memória. **Análise:** Nichado, mas útil.
- 🟢 [inVtero.net](https://github.com/ShaneK2/inVtero.net) — Framework de análise de memória de alta velocidade desenvolvido em .NET. **Análise:** Suporta todos os Windows x64.
- 🟢 [WDBGARK](https://github.com/swwwolf/wdbgark) — Extensão anti-rootkit para WinDBG. **Análise:** Útil para análise de rootkits.
- 🟡 [Rekall](http://www.rekall-forensic.com/) — Framework de análise de memória, fork do Volatility de 2013. **Análise:** Projeto em declínio. Recomendamos Volatility 3.
- 🟡 [BlackLight](https://www.blackbagtech.com/blacklight.html) — Cliente forense Windows/MacOS com suporte a hiberfil, pagefile e análise de memória bruta. **Análise:** Comercial, mas com versão gratuita limitada.

---

## Artefatos do Windows

- 🟢 [AChoir](https://github.com/OMENScan/AChoir) — Script de resposta a incidentes ao vivo para coletar artefatos do Windows. **Análise:** Útil para DFIR.
- 🟢 [python-evt](https://github.com/williballenthin/python-evt) — Biblioteca Python para analisar logs de eventos do Windows. **Análise:** Útil para automação.
- 🟢 [python-registry](https://github.com/williballenthin/python-registry) — Biblioteca Python para analisar arquivos de registro. **Análise:** Essencial para análise de registro.
- 🟢 [RegRipper](https://github.com/keydet89/RegRipper3.0) — Ferramenta de análise de registro baseada em plugins. **Análise:** **Ferramenta padrão** para análise de registro do Windows. A versão 3.0 é a mais recente.

---

## Armazenamento e Workflow

- 🟢 [Viper](https://github.com/viper-framework/viper) — Framework de gerenciamento e análise binária para analistas e pesquisadores. **Análise:** Excelente para organizar amostras e análises.
- 🟢 [stoQ](https://github.com/PUNCH-Cyber/stoq) — Framework de análise de conteúdo distribuído com amplo suporte a plugins. **Análise:** Poderoso para automação.
- 🟢 [FAME](https://github.com/CERT-Polska/fame) — Framework de análise de malware com pipeline extensível. **Análise:** Útil para orquestração.
- 🟢 [Polichombr](https://github.com/ANSSI-FR/polichombr) — Plataforma de análise de malware projetada para ajudar analistas a reverter malwares colaborativamente. **Análise:** Excelente para trabalho em equipe.
- 🟢 [Aleph](https://github.com/merces/aleph) — Sistema de Pipeline de Análise de Malware Open Source. **Análise:** Útil para automação.
- 🟢 [Malwarehouse](https://github.com/sroberts/malwarehouse) — Armazene, marque e pesquise malware. **Análise:** Funcional, mas com desenvolvimento lento.
- 🟡 [CRITs](https://github.com/crits/crits) — Pesquisa Colaborativa em Ameaças, um repositório de malware e ameaças. **Análise:** Poderoso, mas com desenvolvimento estagnado. Alternativa: MISP.


---

## 🤖 IA e LLMs para Análise de Malware

*Ferramentas e frameworks que integram Inteligência Artificial e Modelos de Linguagem de Grande Escala (LLMs) ao fluxo de trabalho de análise de malware.* 🆕

### Análise e Classificação com IA

- 🟢 [VirusTotal Code Insight](https://blog.virustotal.com/) 🤖 — Pipeline de análise baseado em IA que usa Gemini para raciocinar sobre arquivos em tempo real. **Análise:** **Revolucionário.** Já identificou malware que nenhum antivírus detectou. Integrado ao VirusTotal.
- 🟢 [MAD-Agent](https://github.com/) 🤖 — Agente de IA que executa análise automática de malware, combinando análise estática, dinâmica em sandbox e coleta de threat intelligence em tempo real. **Análise:** Pesquisa promissora. Usa MCP (Model Context Protocol) para modularidade.
- 🟢 [MaLAware](https://github.com/) 🤖 — Ferramenta que usa LLMs para traduzir dados brutos de sandbox em descrições legíveis por humanos do comportamento do malware. **Análise:** Excelente para reduzir a carga cognitiva de analistas. Suporta Qwen2.5, Llama, Mistral e Falcon.
- 🟢 [ArA (Artificial Analyst)](https://github.com/) 🤖 — Sistema que combina sandboxing dinâmico com um motor de raciocínio LLM para classificar comportamento como malicioso ou benigno. **Análise:** GPT-4 alcançou 95% de acurácia. Promissor para triagem em SOCs.
- 🟢 [Alpha](https://github.com/) 🤖 — Framework para detecção de malware zero-day que utiliza modelos Transformer e SVMs. **Análise:** Excelente acurácia para ransomware, worms e APTs.
- 🟢 [SaBER-LLMs](https://github.com/) 🤖 — Paradigma que dota LLMs com representação de comportamento consciente de segurança para análise de malware granular. **Análise:** Pesquisa acadêmica promissora.
- 🟢 [PE2Prompt](https://github.com/) 🤖 — Framework nativo de LLM para análise estática interpretável e industrialmente implantável. **Análise:** Aborda a lacuna representacional entre features numéricas e linguagem natural.
- 🟡 [DeepMalDetect](https://github.com/) 🤖 — Modelo de detecção de malware baseado em rede neural profunda (DNN) liberado no GitHub. **Análise:** Acadêmico, mas funcional.
- 🟡 [MalCVE](https://github.com/) 🤖 — Detecção de malware e associação de CVE usando LLMs. **Análise:** 97% de acurácia sem fine-tuning. Custo de $0.03 por arquivo.

### Geração de Regras YARA com IA

- 🟢 [YARAG](https://github.com/) 🤖 — Framework de Geração Aumentada por Recuperação (RAG) para gerar regras YARA de alta fidelidade a partir de metadados de PE do Windows. **Análise:** **Estado da arte.** Reduziu 71 regras candidatas para 18 regras otimizadas com F1 de 84%.
- 🟢 [synthetic-detections/rules](https://github.com/synthetic-detections/rules) 🤖 — Corpus crescente de regras YARA e Snort/Suricata autoradas por IA para campanhas de malware atuais. **Análise:** Excelente recurso com regras validadas e testadas. Cada regra vem com espécimes reproduzíveis.
- 🟢 [LLM-Based YARA Rule Generation](https://github.com/) 🤖 — Pipeline que usa GPT-4o, Llama 3.1 e Gemma 3 para gerar regras YARA de alta qualidade. **Análise:** Pesquisa mostra que GPT-4o oferece o melhor equilíbrio entre cobertura e falsos positivos.

### Engenharia Reversa Assistida por IA

- 🟢 [Kong](https://github.com/) 🤖 — Engenheiro Reverso Agêntico que automatiza a camada mecânica da engenharia reversa usando Ghidra como backend. **Análise:** **Ferramenta impressionante.** Pega um binário ofuscado e completamente stripped e executa um pipeline completo de análise: triagem de funções, construção de contexto de call-graph, recuperação de tipos e símbolos via descompilação guiada por LLM.
- 🟢 [OGhidra](https://github.com/LLNL/OGhidra) 🤖 — Ponte entre LLMs e a plataforma Ghidra, permitindo análise binária conversacional em linguagem natural. **Análise:** Permite análise conversacional de binários. Suporta modelos locais (Ollama) para privacidade total.
- 🟢 [REA (Reverse Engineer Anything)](https://github.com/) 🤖 — Servidor MCP open source que permite que agentes de IA (Claude Code, Codex, Cursor) façam engenharia reversa de binários, apps e capturas de rede. **Análise:** **Fenômeno recente.** Alcançou 115K estrelas no GitHub em uma semana. Capacidade de clonar funcionalidades sem código-fonte.
- 🟢 [CutterMCP+](https://github.com/) 🤖 — Engenharia reversa automatizada via LLMs usando Cutter (GUI para Radare2). **Análise:** Combina o poder do Cutter com LLMs modernos.
- 🟢 [Reversecore MCP](https://github.com/) 🤖 — Servidor MCP com foco em segurança para engenharia reversa, análise de malware e pesquisa de vulnerabilidades. **Análise:** Dá a agentes de IA compatíveis com MCP acesso estruturado a Radare2, r2ghidra, YARA e mais.
- 🟢 [anymous](https://github.com/) 🤖 — Plataforma de engenharia reversa e pentest com 44 agentes de IA. **Análise:** Nichado, mas poderoso.
- 🟢 [LLM and AI plugins for Ghidra](https://github.com/) 🤖 — Vários plugins que integram LLMs ao Ghidra para análise assistida. **Análise:** Ecossistema crescente.
- 🟡 [LLM4Decompile](https://github.com/) 🤖 — Modelos de LLM especificamente treinados para descompilação de código binário. **Análise:** Pesquisa acadêmica.

### Forense de Memória com IA

- 🟢 [Leveraging LLMs for Memory Forensics](https://github.com/) 🤖 — Integração de inteligência baseada em LLM em fluxos de trabalho de forense de memória. **Análise:** Avalia GPT-4o, o1, Gemini 2.0 Flash, Grok 3. Promissor para acelerar a triagem de memória.

---

## Miscelânea

- 🟢 [FLARE VM](https://github.com/mandiant/flare-vm) — Distribuição de segurança baseada em Windows, totalmente personalizável, para análise de malware. **Análise:** **Indispensável.** O ambiente padrão para análise de malware no Windows.
- 🟢 [REMnux](https://remnux.org/) — Distribuição Linux e imagens Docker para engenharia reversa e análise de malware. **Análise:** **Indispensável.** O ambiente padrão para análise de malware no Linux.
- 🟢 [Tsurugi Linux](https://tsurugi-linux.org/) — Distribuição Linux projetada para apoiar investigações de DFIR, análise de malware e atividades de OSINT. **Análise:** Excelente alternativa ao REMnux.
- 🟢 [Santoku Linux](https://santoku-linux.com/) — Distribuição Linux para forense móvel, análise de malware e segurança. **Análise:** Nichado para mobile.
- 🟢 [Pafish](https://github.com/a0rtega/pafish) — Paranoid Fish, ferramenta de demonstração que emprega várias técnicas para detectar sandboxes e ambientes de análise. **Análise:** Útil para testar a robustez do seu sandbox.
- 🟢 [al-khaser](https://github.com/LordNoteworthy/al-khaser) — PoC de malware com boas intenções que visa testar sistemas anti-malware. **Análise:** Útil para testar detecção.
- 🟢 [DC3-MWCP](https://github.com/Defense-Cyber-Crime-Center/DC3-MWCP) — Framework de Parser de Configuração de Malware do Defense Cyber Crime Center. **Análise:** Útil para extração de configurações.
- 🟢 [Malware Organiser](https://github.com/uppusaikiran/malware-organiser) — Ferramenta simples para organizar grandes arquivos maliciosos/benignos. **Análise:** Utilitário.
- 🟢 [CryptoKnight](https://github.com/AbertayMachineLearningGroup/CryptoKnight) — Framework automatizado de engenharia reversa e classificação de algoritmos criptográficos. **Análise:** Nichado, mas poderoso.
- 🟢 [MalSploitBase](https://github.com/misterch0c/malSploitBase) — Banco de dados contendo exploits usados por malware. **Análise:** Recurso de referência.
- 🟢 [Malware Museum](https://archive.org/details/malwaremuseum) — Coleção de programas de malware distribuídos nas décadas de 1980 e 1990. **Análise:** Valor histórico.

---

## Recursos

### Livros

*Material essencial de leitura sobre análise de malware.*

- 🟢 [Practical Malware Analysis](https://amzn.com/dp/1593272901) — The Hands-On Guide to Dissecting Malicious Software. **Análise:** **A bíblia da análise de malware.** Ainda extremamente relevante.
- 🟢 [The Art of Memory Forensics](https://amzn.com/dp/1118825098) — Detecting Malware and Threats in Windows, Linux, and Mac Memory. **Análise:** **Indispensável** para forense de memória.
- 🟢 [Practical Reverse Engineering](https://www.amzn.com/dp/1118787315/) — Intermediate Reverse Engineering. **Análise:** Excelente para aprofundar em RE.
- 🟢 [Malware Analyst's Cookbook and DVD](https://amzn.com/dp/0470613033) — Tools and Techniques for Fighting Malicious Code. **Análise:** Clássico, ainda muito útil.
- 🟢 [The IDA Pro Book](https://amzn.com/dp/1593272898) — The Unofficial Guide to the World's Most Popular Disassembler. **Análise:** Referência para IDA.
- 🟢 [Rootkits and Bootkits](https://www.amazon.com/dp/1593277164) — Reversing Modern Malware and Next Generation Threats. **Análise:** Nichado, mas excelente.
- 🟢 [Learning Malware Analysis](https://www.packtpub.com/networking-and-servers/learning-malware-analysis) — Explore os conceitos, ferramentas e técnicas para analisar e investigar malware Windows. **Análise:** Bom para iniciantes.
- 🟢 [Mastering Malware Analysis](https://www.packtpub.com/networking-and-servers/mastering-malware-analysis) — Guia completo do analista de malware. **Análise:** Abrangente.
- 🟢 [Mastering Reverse Engineering](https://www.packtpub.com/networking-and-servers/mastering-reverse-engineering) — Re-engenheire suas habilidades de hacking ético. **Análise:** Útil.
- 🟢 [Real Digital Forensics](https://www.amzn.com/dp/0321240693) — Computer Security and Incident Response. **Análise:** Clássico de DFIR.
- 🟢 [The Rootkit Arsenal](https://amzn.com/dp/144962636X) — Escape and Evasion in the Dark Corners of the System. **Análise:** Clássico.

### Outros

- 🟢 [APT Notes](https://github.com/aptnotes/data) — Uma coleção de papers e notas relacionadas a Advanced Persistent Threats. **Análise:** Excelente recurso.
- 🟢 [Malware Samples and Traffic](http://malware-traffic-analysis.net/) — Este blog foca em tráfego de rede relacionado a infecções por malware. **Análise:** Excelente para praticar análise de tráfego.
- 🟢 [Malware Analysis Tutorials](http://fumalwareanalysis.blogspot.nl/p/malware-analysis-tutorials-reverse.html) — Tutoriais de análise de malware do Dr. Xiang Fu. **Análise:** Recurso clássico para aprendizado prático.
- 🟢 [RPISEC Malware Analysis](https://github.com/RPISEC/Malware) — Materiais do curso de Análise de Malware do Rensselaer Polytechnic Institute. **Análise:** Excelente material de curso.
- 🟢 [Practical Malware Analysis Starter Kit](https://bluesoul.me/practical-malware-analysis-starter-kit/) — Pacote com a maioria dos softwares referenciados no livro Practical Malware Analysis. **Análise:** Muito útil para configurar o ambiente.
- 🟢 [Honeynet Project](http://honeynet.org/) — Ferramentas, papers e outros recursos sobre honeypots. **Análise:** Recurso clássico.
- 🟢 [Kernel Mode](http://www.kernelmode.info/forum/) — Comunidade ativa dedicada à análise de malware e desenvolvimento de kernel. **Análise:** Fórum de nicho.
- 🟢 [Malicious Software](https://zeltser.com/malicious-software/) — Blog e recursos sobre malware por Lenny Zeltser. **Análise:** Referência na área.
- 🟢 [Malware Analysis Search](https://cse.google.com/cse/home?cx=011750002002865445766%3Apc60zx1rliu) — Motor de busca personalizado do Google por Corey Harrell. **Análise:** Útil para pesquisa.
- 🟢 [Malware Persistence](https://github.com/Karneades/malware-persistence) — Coleção de informações focadas em persistência de malware. **Análise:** Excelente recurso.
- 🟢 [Ember](https://github.com/endgameinc/ember) — Endgame Malware BEnchmark for Research, um repositório que facilita a criação de um modelo de machine learning para prever um score para um arquivo PE. **Análise:** Excelente para pesquisa em ML.
- 🟢 [File Formats posters](https://github.com/corkami/pics) — Visualização de formatos de arquivo comuns (incluindo PE e ELF). **Análise:** Referência visual útil.
- 🟢 [Windows Registry specification](https://github.com/msuhanov/regf/blob/master/Windows%20registry%20file%20format%20specification.md) — Especificação do formato de arquivo do registro do Windows. **Análise:** Referência técnica.
- 🟢 [/r/csirt_tools](https://www.reddit.com/r/csirt_tools/) — Subreddit para ferramentas e recursos de CSIRT. **Análise:** Comunidade ativa.
- 🟢 [/r/Malware](https://www.reddit.com/r/Malware) — O subreddit de malware. **Análise:** Comunidade ativa.
- 🟢 [/r/ReverseEngineering](https://www.reddit.com/r/ReverseEngineering) — Subreddit de engenharia reversa. **Análise:** Comunidade ativa.
- 🟢 [Malware Analysis, Threat Intelligence and Reverse Engineering](https://www.slideshare.net/bartblaze/malware-analysis-threat-intelligence-and-reverse-engineering) — Apresentação introdutória aos conceitos. **Análise:** Útil para iniciantes.
- 🟢 [Malware Search+++](https://addons.mozilla.org/fr/firefox/addon/malware-search-plusplusplus/) — Extensão Firefox que permite pesquisar facilmente em alguns dos bancos de dados de malware mais populares. **Análise:** Conveniente.
- 🟢 [WindowsIR: Malware](http://windowsir.blogspot.com/p/malware.html) — Página de Harlan Carvey sobre Malware. **Análise:** Blog de referência.



