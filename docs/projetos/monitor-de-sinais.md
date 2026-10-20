[← Voltar ao portfólio](../../README.md)

# Monitor de Sinais

**Aplicação desktop · simulador e aquisição serial · Python e Qt**

Visualização local da amplitude de sinais ao longo do tempo, com simulador ajustável, entrada serial e controles de exploração do gráfico.

![Diagrama do fluxo: selecionar a fonte, adquirir amostras, explorar e analisar.](../../assets/projetos/monitor-de-sinais.svg)

## Objetivo

Tornar um fluxo de amostras compreensível em uma interface: acompanhar a curva, observar estatísticas e identificar estados de conexão. O simulador permite explorar o aplicativo sem depender de uma placa física.

## Como funciona

1. **Selecionar a fonte:** escolher simulador ou entrada serial compatível com o contrato NDJSON.
2. **Adquirir amostras:** iniciar a leitura e acompanhar o estado da fonte.
3. **Explorar o gráfico:** pausar a visualização, ajustar o zoom e retornar à janela atual.
4. **Analisar:** consultar estatísticas e contadores de recebimento, erros e descartes.

No simulador, é possível mudar a intensidade artificial e pausar a curva para observá-la. A aquisição continua durante a pausa visual; ao retornar, o gráfico mostra a janela recente.

## Decisões técnicas

- **Fontes explícitas:** uma falha serial não provoca troca automática para simulação.
- **Aquisição e visualização separadas:** a pausa do gráfico não interrompe a chegada de amostras.
- **Limites de memória:** janela e fila têm limites; descartes por sobrecarga são contabilizados.
- **Execução local:** o aplicativo não depende de conta ou serviço online para funcionar.

## Validação e limites

A documentação registra testes automatizados, ensaios com dados sintéticos e verificações de empacotamento no Linux e em CI Windows. Os testes Windows usam Qt sem janela; a inspeção visual nativa no Windows 10/11 permanece pendente.

A integração com placa física e firmware ainda não foi validada. A amplitude é expressa em contagens do ADC, sem equivalência estabelecida com tensão, força ou atividade fisiológica. O aplicativo não constitui validação médica ou elétrica da montagem.

## Tecnologias e aprendizado

**Python · PySide6/Qt · PyQtGraph · NumPy · pySerial**

O projeto reúne prática em aquisição de dados, protocolos, gráficos e estados de conexão. Desenvolvimento com apoio de ferramentas de IA; programação manual em nível básico e aprendizado contínuo.

[Código e instruções](https://github.com/NGK-999/InterfaceNeural) · [Evidências e limites](https://github.com/NGK-999/InterfaceNeural/blob/main/docs/verificacao.md) · [Contrato serial](https://github.com/NGK-999/InterfaceNeural/blob/main/docs/protocolo.md)
