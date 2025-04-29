# Segurança de Rede: VPNs, DNS Seguro e Tor

Sua conexão com a internet é a ponte entre seu dispositivo e o mundo online. Proteger essa conexão é vital para evitar que seu Provedor de Serviços de Internet (ISP), administradores de rede (em redes Wi-Fi públicas, trabalho ou escola) ou até mesmo agentes mal-intencionados espionem sua atividade, bloqueiem seu acesso ou interceptem seus dados. Esta seção aborda três tecnologias chave para segurança de rede: VPNs, DNS Seguro e a rede Tor.

## VPNs (Redes Privadas Virtuais)

Uma VPN cria um "túnel" criptografado entre seu dispositivo e um servidor operado pelo provedor de VPN. Todo o seu tráfego de internet passa por esse túnel, ocultando sua atividade do seu ISP local e alterando seu endereço IP público para o do servidor VPN.

**O que uma VPN FAZ:**

*   **Criptografa seu tráfego:** Impede que seu ISP ou administradores de rede local vejam os sites que você visita ou o conteúdo do seu tráfego (exceto o fato de que você está conectado a uma VPN).
*   **Mascara seu endereço IP:** Sites e serviços que você acessa verão o endereço IP do servidor VPN, não o seu IP real. Isso ajuda a contornar restrições geográficas e dificulta o rastreamento baseado em IP.
*   **Protege em redes Wi-Fi públicas:** Criptografa sua conexão em redes não confiáveis (cafés, aeroportos), protegendo contra espionagem local.

**O que uma VPN NÃO FAZ (Mitos Comuns):**

*   **Não garante anonimato total:** Seu provedor de VPN *pode* ver sua atividade se ele mantiver logs. Você está transferindo a confiança do seu ISP para o provedor de VPN. Além disso, VPNs não protegem contra rastreamento por cookies, fingerprinting do navegador ou login em contas.
*   **Não protege contra malware ou phishing:** Uma VPN não impede que você baixe arquivos maliciosos ou insira suas credenciais em sites falsos.
*   **Não necessariamente aumenta a velocidade:** Embora possa contornar limitações de velocidade impostas pelo ISP (throttling), a criptografia e o roteamento adicional podem, em alguns casos, diminuir a velocidade da conexão.

**Critérios de Escolha para uma VPN Confiável:**

A escolha de um provedor de VPN é crucial, pois você está confiando seus dados a ele.

*   **Política de Logs (No-Logs Auditada):** A VPN deve ter uma política clara de *não* registrar sua atividade online (sites visitados, timestamps, IPs). Idealmente, essa política deve ser verificada por auditorias independentes de terceiros.
*   **Jurisdição:** A localização legal da empresa VPN importa. Países com leis de retenção de dados ou que fazem parte de alianças de vigilância (como os 5/9/14 Eyes) podem representar um risco maior.
*   **Protocolos de Criptografia Fortes:** Deve oferecer protocolos modernos e seguros como OpenVPN e WireGuard. Evite protocolos obsoletos como PPTP.
*   **Kill Switch:** Um recurso essencial que bloqueia todo o tráfego de internet se a conexão VPN cair inesperadamente, evitando que seu IP real seja exposto.
*   **Proteção Contra Vazamentos (DNS, WebRTC, IPv6):** A VPN deve garantir que seu DNS, endereço IP real (via WebRTC) ou tráfego IPv6 não vazem fora do túnel VPN.
*   **Modelo de Pagamento e Privacidade:** Provedores que aceitam pagamentos anônimos (criptomoedas, dinheiro) e exigem informações mínimas de registro são preferíveis.
*   **Código Aberto (Plus):** Clientes VPN de código aberto permitem maior escrutínio da comunidade.
*   **Reputação e Transparência:** Pesquise sobre a empresa, sua história e a transparência de suas operações.

**Exemplos de Provedores Bem Avaliados (Baseado em Fontes Confiáveis como Privacy Guides):**

*   **ProtonVPN:**
    *   **Prós:** Sediado na Suíça (forte legislação de privacidade), política de no-logs auditada, código aberto, forte foco em segurança, oferece plano gratuito limitado.
    *   **Contras:** Planos pagos podem ser um pouco mais caros.
    *   [![ProtonVPN](https://img.shields.io/badge/VPN-ProtonVPN-6D4AFF?style=for-the-badge&logo=protonvpn&logoColor=white)](https://protonvpn.com/)
*   **Mullvad:**
    *   **Prós:** Sediado na Suécia, política estrita de no-logs (auditada), aceita pagamentos anônimos (dinheiro, cripto), não exige email para registro (usa números de conta aleatórios), focado exclusivamente em VPN, código aberto.
    *   **Contras:** Menos servidores que alguns concorrentes.
    *   [![Mullvad](https://img.shields.io/badge/VPN-Mullvad-008174?style=for-the-badge&logo=mullvad&logoColor=white)](https://mullvad.net/pt)
*   **IVPN:**
    *   **Prós:** Sediado em Gibraltar, política de no-logs auditada, código aberto, aceita pagamentos anônimos, forte compromisso com a transparência.
    *   **Contras:** Interface pode ser menos intuitiva para iniciantes.
    *   [![IVPN](https://img.shields.io/badge/VPN-IVPN-00938A?style=for-the-badge)](https://www.ivpn.net/)

**Riscos e Limitações das VPNs:**

*   **Confiança no Provedor:** O maior risco é escolher um provedor não confiável que mantenha logs ou tenha segurança fraca.
*   **VPNs Gratuitas:** Desconfie de VPNs gratuitas. Elas geralmente ganham dinheiro vendendo seus dados, exibindo anúncios ou tendo segurança inadequada.
*   **Falsa Sensação de Segurança:** Lembre-se que VPNs não resolvem todos os problemas de privacidade (cookies, fingerprinting, etc.).

## DNS Seguro e Privado (DoH/DoT)

O DNS (Domain Name System) é como a lista telefônica da internet. Quando você digita um endereço como `www.exemplo.com`, seu dispositivo consulta um servidor DNS para obter o endereço IP correspondente. Tradicionalmente, essas consultas são feitas em texto plano (sem criptografia), permitindo que seu ISP ou qualquer pessoa na rede veja quais sites você está tentando acessar.

**Problemas de Privacidade com DNS Padrão:**

*   **Espionagem:** Seu ISP pode registrar todos os sites que você visita.
*   **Censura/Bloqueio:** ISPs ou governos podem bloquear o acesso a determinados sites no nível do DNS.
*   **Manipulação:** Servidores DNS maliciosos podem redirecioná-lo para sites falsos (phishing).

**Tecnologias de DNS Seguro:**

*   **DNS over HTTPS (DoH):** Encapsula as consultas DNS dentro de tráfego HTTPS normal (porta 443). Isso as torna indistinguíveis do tráfego web comum, dificultando o bloqueio e a espionagem.
*   **DNS over TLS (DoT):** Usa uma conexão TLS dedicada (porta 853) para criptografar as consultas DNS. É mais fácil de bloquear por firewalls, mas é um padrão dedicado para DNS seguro.

**Provedores de DNS Recomendados (Foco em Privacidade):**

*   **Quad9:**
    *   **Prós:** Focado em segurança, bloqueia domínios maliciosos conhecidos, operado por uma organização sem fins lucrativos suíça, forte política de privacidade (não registra IPs).
    *   **Contras:** Pode bloquear alguns sites legítimos por engano (raro).
    *   **Endereços (DoH):** `https://dns.quad9.net/dns-query`
    *   **Endereços (DoT):** `dns.quad9.net`
    *   [![Quad9](https://img.shields.io/badge/DNS-Quad9-2F2E60?style=for-the-badge)](https://www.quad9.net/)
*   **NextDNS:**
    *   **Prós:** Altamente configurável, permite criar perfis personalizados com listas de bloqueio (anúncios, rastreadores, malware), oferece análises (com opções de privacidade), plano gratuito generoso.
    *   **Contras:** Requer criação de conta para configuração avançada, logs são mantidos (mas podem ser desativados ou limitados).
    *   **Endereços (DoH/DoT):** Personalizados por conta.
    *   [![NextDNS](https://img.shields.io/badge/DNS-NextDNS-1E88E5?style=for-the-badge)](https://nextdns.io/)
*   **Cloudflare DNS:**
    *   **Prós:** Rápido, amplamente disponível, promete não vender dados e apagar logs após 24h (auditado).
    *   **Contras:** Cloudflare é uma grande empresa de infraestrutura de internet, o que gera preocupações sobre centralização de dados para alguns usuários.
    *   **Endereços (DoH):** `https://cloudflare-dns.com/dns-query`
    *   **Endereços (DoT):** `1dot1dot1dot1.cloudflare-dns.com`
    *   [![Cloudflare DNS](https://img.shields.io/badge/DNS-Cloudflare-F38020?style=for-the-badge&logo=cloudflare)](https://1.1.1.1/)

**Como Configurar DNS Seguro:**

A configuração pode ser feita em diferentes níveis:

*   **No Navegador:** Muitos navegadores (Firefox, Brave, Chrome, Edge) suportam DoH nativamente. Procure por "DNS Seguro" ou "DNS over HTTPS" nas configurações de privacidade/segurança.
*   **No Sistema Operacional:**
    *   **Windows 11:** Suporte nativo para DoH.
    *   **macOS Ventura+:** Suporte nativo para DoH/DoT.
    *   **Linux:** Requer configuração manual ou software adicional (como `systemd-resolved`).
    *   **Android 9+:** Suporte nativo para DoT ("DNS Privado").
    *   **iOS 14+:** Suporte nativo para DoH/DoT via perfis de configuração ou aplicativos.
*   **No Roteador:** Alguns roteadores permitem configurar DoH/DoT para toda a rede doméstica.

Configurar no nível do sistema operacional ou roteador protege todo o tráfego do dispositivo/rede, enquanto a configuração no navegador protege apenas o tráfego daquele navegador.

## Tor (The Onion Router)

Tor é uma rede descentralizada e operada por voluntários que permite navegar na internet de forma mais anônima. Ele funciona roteando seu tráfego através de uma série de três servidores (nós) aleatórios, criptografando-o em camadas (como uma cebola) a cada salto.

**Como Funciona:**

1.  **Nó de Entrada (Guard Node):** Conhece seu IP real, mas não o destino final.
2.  **Nó do Meio (Middle Node):** Recebe tráfego do nó de entrada e o envia para o nó de saída. Não conhece seu IP nem o destino final.
3.  **Nó de Saída (Exit Node):** Envia seu tráfego para o destino final na internet. Conhece o destino, mas não seu IP real. O site de destino vê o IP do nó de saída.

**Casos de Uso:**

*   **Anonimato:** Dificulta muito que sites rastreiem sua localização real ou que seu ISP veja o que você está acessando.
*   **Contornar Censura:** Permite acessar sites bloqueados em sua região.
*   **Proteção Contra Vigilância:** Usado por jornalistas, ativistas e cidadãos em regimes opressivos.

**Tor Browser:**

A maneira mais fácil e segura de usar a rede Tor é através do **Tor Browser**, uma versão modificada do Firefox pré-configurada para rotear todo o tráfego pela rede Tor e incluir proteções adicionais contra fingerprinting.

*   **Instruções:** Baixe do site oficial [torproject.org](https://www.torproject.org/). Não instale extensões adicionais, pois podem comprometer o anonimato.
*   **Limitações:** A navegação pode ser mais lenta devido ao roteamento adicional. Alguns sites podem bloquear o acesso de IPs de nós de saída Tor conhecidos ou apresentar CAPTCHAs com mais frequência.
*   [![Tor Browser](https://img.shields.io/badge/Navegador-Tor%20Browser-7D4698?style=for-the-badge&logo=torproject)](https://www.torproject.org/)

**Riscos da Rede Tor:**

*   **Nós de Saída Maliciosos:** Qualquer pessoa pode operar um nó de saída. Nós maliciosos podem tentar espionar tráfego não criptografado (HTTP) ou injetar malware. **Sempre use HTTPS ao navegar pela Tor.**
*   **Timing Attacks:** Adversários que controlam ambos os nós de entrada e saída (ou monitoram o tráfego de/para eles) podem, teoricamente, correlacionar o tempo do tráfego para tentar desanonimizar usuários (difícil, mas possível para adversários poderosos).
*   **Comprometimento do Navegador:** Vulnerabilidades no próprio Tor Browser (embora raras) podem expor o usuário.

**Tor vs VPN:**

| Característica      | VPN                                  | Tor                                      |
| :------------------ | :----------------------------------- | :--------------------------------------- |
| **Objetivo Principal** | Privacidade contra ISP/Rede Local | Anonimato contra Sites/Vigilância        |
| **Confiança**       | Confia no provedor VPN               | Confia na rede descentralizada (design)  |
| **Roteamento**      | Ponto único (Servidor VPN)           | Múltiplos saltos (3 nós aleatórios)      |
| **Velocidade**      | Geralmente mais rápida               | Geralmente mais lenta                    |
| **IP de Saída**     | Fixo (do servidor VPN)               | Variável (do nó de saída aleatório)      |
| **Bloqueio**        | Menos provável de ser bloqueado      | Mais provável de ser bloqueado por sites |
| **Custo**           | Geralmente pago                      | Gratuito                                 |

**Usar VPN com Tor?** É possível (VPN -> Tor ou Tor -> VPN), mas geralmente não recomendado para a maioria dos usuários, pois adiciona complexidade e potenciais novos pontos de falha sem um benefício claro de anonimato na maioria dos cenários. O Tor Browser por si só oferece um bom nível de anonimato para a maioria das necessidades.

Ao combinar o uso criterioso de VPNs, a configuração de DNS seguro e, quando necessário, a rede Tor, você pode fortalecer significativamente a segurança e a privacidade da sua conexão à internet.

