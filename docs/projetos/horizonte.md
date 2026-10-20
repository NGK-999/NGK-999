[← Voltar ao portfólio](../../README.md)

# Horizonte

**Visualização no navegador · demonstração técnica · TypeScript e WebGL**

Experiência interativa de um buraco negro, com câmera livre, matéria procedural e controles de apresentação.

![Diagrama do fluxo: ajustar a câmera, calcular trajetórias, compor a cena e explorar.](../../assets/projetos/horizonte.svg)

## Objetivo

Explorar renderização no navegador a partir de um modelo de Schwarzschild, conectando cálculo de trajetórias, composição visual e interação. A experiência combina um modelo óptico com escolhas artísticas para a matéria e a emissão.

## Como funciona

1. **Ajustar a câmera:** escolher enquadramento, órbita e zoom.
2. **Calcular trajetórias:** o shader reconstrói os raios e integra suas trajetórias.
3. **Compor a cena:** combinar disco, céu procedural, brilho e saída de cor.
4. **Explorar:** controlar movimento da matéria, exposição, qualidade e apresentação.

Um exemplo é pausar a matéria e mover apenas a câmera para comparar a aparência da cena em diferentes ângulos.

## Decisões técnicas

- **Controles independentes:** câmera, matéria e apresentação têm estados separados.
- **Qualidade adaptável:** a resolução interna pode variar conforme o desempenho.
- **Movimento reduzido:** a preferência do navegador é respeitada na inicialização.
- **Disponibilidade explícita:** dispositivos sem os recursos WebGL exigidos recebem uma indicação de indisponibilidade.

## Validação e limites

A documentação registra verificações de tipos, compilação, testes de matemática e relógios e testes automatizados de interação no Chromium. Foram examinadas capturas em diferentes ângulos e uma configuração móvel emulada.

Não houve validação de Safari, Firefox ou celular físico. O desempenho depende da GPU e das configurações. A emissão e a matéria são procedurais e artísticas; a demonstração não é uma previsão científica calibrada.

## Tecnologias e aprendizado

**TypeScript · Three.js · WebGL2 · GLSL · Vite · Playwright**

O projeto reúne prática em visualização, estados de interação e verificação de aplicações gráficas. Desenvolvimento com apoio de ferramentas de IA; programação manual em nível básico e aprendizado contínuo.

[Código e execução local](https://github.com/NGK-999/horizonte-buraco-negro#executar-localmente) · [Evidências e limitações](https://github.com/NGK-999/horizonte-buraco-negro/blob/trabalho/buraco-negro/docs/VALIDACAO.md)
