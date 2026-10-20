[← Voltar ao portfólio](../../README.md)

# coolleo-display-linux

**Integração com hardware · experimental · Linux e USB HID**

Serviço que obtém temperatura e potência de uma CPU Intel no Linux e envia esses valores a um modelo específico de display USB.

![Diagrama do fluxo: ler sensores, preparar dados, validar o dispositivo e enviar por USB.](../../assets/projetos/coolleo-display-linux.svg)

## Objetivo

Explorar a integração de um display de telemetria com Linux, usando os sensores do sistema e o protocolo USB observado no dispositivo. O suporte é restrito ao hardware documentado pelo projeto.

## Como funciona

1. **Ler sensores:** obter temperatura via `coretemp` e potência do pacote via Intel RAPL.
2. **Preparar os dados:** montar o relatório com os valores no formato documentado.
3. **Validar o dispositivo:** conferir identificação USB e descritor HID antes do envio.
4. **Enviar ao display:** transmitir pelo dispositivo `hidraw` e repetir o ciclo pelo serviço.

O fluxo lê os sensores a cada dois segundos. A conferência final consiste em comparar os valores enviados com os números apresentados no display físico.

## Decisões técnicas

- **Compatibilidade restrita:** o dispositivo deve corresponder à identificação e ao descritor HID esperados.
- **Sem dependência online:** a implementação Python usa a biblioteca padrão e não inclui comunicação de rede.
- **Serviço com permissões limitadas:** instalação com `systemd` e regras específicas para acesso ao dispositivo.
- **Escopo definido:** o programa envia telemetria; não controla ventoinhas, bomba, RGB ou firmware.

## Validação e limites

A documentação registra leitura dos sensores, identificação do dispositivo e observação do transporte USB em uma unidade. A confirmação independente de que os números do display acompanham os valores do Linux continua pendente.

O estado é experimental, parcialmente validado. O projeto documenta suporte ao dispositivo USB `1a2c:4d84` com o descritor esperado e a sensores Intel; não afirma compatibilidade com AMD ou outros modelos de display.

## Tecnologias e aprendizado

**Python · Shell · Linux · systemd · udev · USB HID**

O projeto reúne prática em sensores, serviços Linux e integração com um protocolo de hardware. Desenvolvimento com apoio de ferramentas de IA; programação manual em nível básico e aprendizado contínuo.

[Código](https://github.com/NGK-999/coolleo-display-linux) · [Guia em português](https://github.com/NGK-999/coolleo-display-linux/blob/main/README.pt-BR.md) · [Protocolo e evidências](https://github.com/NGK-999/coolleo-display-linux/blob/main/docs/PROTOCOL.md)
