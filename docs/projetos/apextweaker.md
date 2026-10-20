[← Voltar ao portfólio](../../README.md)

# ApexTweaker

**Aplicação desktop · Windows · C#, .NET e WPF**

Diagnóstico, telemetria e ajustes reversíveis reunidos em uma interface para explorar configurações do Windows e preparar ambientes de Minecraft.

![Diagrama do fluxo: diagnosticar, preparar, avaliar e restaurar.](../../assets/projetos/apextweaker.svg)

## Objetivo

Dar contexto às alterações de configuração: observar o computador, escolher um ajuste e ter um caminho de restauração. O projeto inclui um modo demonstração para explorar a interface sem modificar o Windows.

## Como funciona

1. **Diagnosticar:** consultar informações do hardware e indicadores de configuração.
2. **Preparar:** selecionar ajustes ou um perfil de Minecraft, com os recursos de backup do projeto.
3. **Avaliar:** observar telemetria e comparar o comportamento após uma alteração.
4. **Restaurar:** utilizar os registros e recursos de reversão quando necessário.

Um exemplo de uso é examinar a configuração atual antes de preparar um perfil de Minecraft, testar o resultado e restaurar a configuração anterior se o ajuste não for útil.

## Decisões técnicas

- **Modo demonstração:** bloqueia alterações no Windows durante a exploração da interface.
- **Reversão:** snapshots e registros das alterações permitem acompanhar o que foi aplicado.
- **Preparação de Minecraft:** backup e restauração fazem parte do fluxo documentado.
- **Interface desktop:** WPF apresenta diagnóstico, módulos, telemetria e utilidades no mesmo aplicativo.

## Validação e limites

O repositório documenta comandos de compilação e autotestes para demonstração, catálogo e Minecraft. Essa apresentação descreve os recursos e os procedimentos disponíveis; não representa uma nova execução desses testes.

O desempenho depende do computador, dos jogos e das configurações. O projeto não apresenta um ganho universal de FPS como resultado comprovado.

## Tecnologias e aprendizado

**C# · .NET · WPF · integração com recursos do Windows**

O projeto reúne prática em interfaces desktop, diagnóstico, organização de configurações e reversão de alterações. Desenvolvimento com apoio de ferramentas de IA; programação manual em nível básico e aprendizado contínuo.

[Código e instruções](https://github.com/NGK-999/tweaker) · [Documentação técnica](https://github.com/NGK-999/tweaker/blob/main/docs/README.md)
