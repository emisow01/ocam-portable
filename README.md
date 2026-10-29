# oCam Portable (Clean Edition)

Versão portátil, autônoma e limpa do gravador de tela **oCam Screen Recorder**, completamente livre de anúncios, telemetria, conexões web e processos em segundo plano.

---

## 🚀 Características

- **100% Portátil:** Não necessita de instalação ou privilégios de administrador. Execute diretamente de qualquer pasta ou pendrive USB.
- **Sem Anúncios:** Motor WebView2/Edge, pop-ups de compra, banners publicitários e telas de encerramento foram totalmente removidos.
- **Interface Compacta:** Janela principal reduzida apenas à barra de ferramentas de gravação (135px de altura, sem espaço vazio de publicidade).
- **Zero Conexões Web:** Telemetria, verificações automáticas de atualização e timers de polling desativados.
- **Leve e Eficiente:** Consumo de memória RAM reduzido para aproximadamente **~27 MB** (contra mais de 200 MB da versão original com WebView2).
- **Encerramento Limpo:** Ao fechar a aplicação, todos os processos e threads são encerrados de forma imediata e definitiva, sem processos órfãos em segundo plano.

---

## 🛠️ Modificações Técnicas

1. **Desacoplamento do Serviço de Segundo Plano:** Eliminada a dependência do executável auxiliar `oCamTask.exe` e do gate de verificação do switch `/Run`.
2. **Modo Comercial / Registrado:** Flag interna de licenciamento forçada para o modo comercial, desativando todas as rotinas de adware da interface Delphi.
3. **Neutralização do WebView2:** Eliminada a carga do `WebView2Loader.dll` e do componente de navegador integrado.
4. **Desativação de Updaters e Timers:** Anulada a criação da thread de verificação de atualizações (`CheckUpdate`) e do timer periódico de 10 segundos.
5. **Redirecionamento de Domínios:** Todas as referências aos servidores do desenvolvedor original (`ohsoft.net`) foram redirecionadas para `127.0.0.1`.
6. **Encerramento Seguro:** Rotinas de saída ajustadas para invocar diretamente a finalização da aplicação (`System.@Halt0`), garantindo que o processo seja 100% finalizado ao clicar em Fechar ou Sair.

---

## 📁 Estrutura de Arquivos

```text
oCam_Portable/
├── oCam.exe                 # Executável principal portátil e modificado
├── language/                # Pacotes de tradução (Português, Inglês, Espanhol, etc.)
├── LibSSL/                  # Bibliotecas de criptografia local
├── v550.0x86/               # Codecs, encoders FFmpeg e captura de tela (32-bit)
├── v550.0x64/               # Codecs, encoders FFmpeg e captura de tela (64-bit)
├── .gitignore
└── README.md
```

---

## 🎮 Como Usar

1. Execute o arquivo `oCam.exe`.
2. Posicione a área verde de captura sobre a região da tela que deseja gravar (ou selecione tela inteira / janela).
3. Utilize os botões da barra superior ou os atalhos de teclado para controlar a gravação.

### Atalhos Padrão de Teclado

| Ação | Tecla Padrão |
| :--- | :--- |
| **Gravar / Parar** | `F2` |
| **Pausar / Retomar** | `Shift + F2` |
| **Capturar Tela (Screenshot)** | `F3` |
| **Selecionar Área Alvo** | `F4` |

---

## ⚙️ Requisitos do Sistema

- **Sistema Operacional:** Windows 7 / 8 / 10 / 11 (32-bit ou 64-bit)
- **DirectX:** Versão 9.0c ou superior (para captura de jogos/tela acelerada por hardware)
- **Armazenamento:** Aproximadamente ~35 MB livres
