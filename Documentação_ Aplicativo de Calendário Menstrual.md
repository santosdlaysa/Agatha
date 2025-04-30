# Documentação: Aplicativo de Calendário Menstrual

## Introdução

Este documento fornece uma visão geral detalhada do aplicativo de Calendário Menstrual, desenvolvido para ajudar usuárias a registrar seus ciclos menstruais, visualizar informações em um calendário e obter previsões sobre períodos férteis e próximas menstruações. O aplicativo foi construído utilizando tecnologias web modernas, focando em uma interface intuitiva e na privacidade dos dados da usuária, que são armazenados exclusivamente no navegador local.

O objetivo principal é oferecer uma ferramenta simples e eficaz para o acompanhamento do ciclo menstrual, fornecendo informações úteis baseadas nos dados registrados pela própria usuária. A aplicação calcula estimativas que podem auxiliar no planejamento familiar ou simplesmente no autoconhecimento do corpo.



## Funcionalidades Principais

O aplicativo oferece as seguintes funcionalidades:

1.  **Registro de Menstruação:** Permite que a usuária insira a data de início e a duração (em dias) de cada ciclo menstrual.
2.  **Visualização em Calendário:** Exibe um calendário mensal onde os dias de menstruação registrados são destacados (vermelho). Além disso, o calendário mostra visualmente o período fértil estimado (azul) e a data prevista para a próxima menstruação (borda roxa).
3.  **Cálculo do Ciclo Fértil:** Com base nos registros anteriores, o aplicativo estima a janela fértil, que são os dias com maior probabilidade de ovulação.
4.  **Previsão da Próxima Menstruação:** Utilizando a média da duração dos ciclos registrados, o aplicativo calcula e exibe a data estimada para o início da próxima menstruação.
5.  **Informações do Ciclo:** Um painel dedicado exibe as datas estimadas para a janela fértil, o período de alta probabilidade de gravidez e a próxima menstruação.
6.  **Armazenamento Local:** Todos os dados inseridos pela usuária são salvos diretamente no armazenamento local (localStorage) do navegador, garantindo a privacidade, pois os dados não saem do dispositivo da usuária.



## Tecnologias Utilizadas

O aplicativo foi desenvolvido com as seguintes tecnologias:

*   **React:** Biblioteca JavaScript para construção de interfaces de usuário.
*   **Vite:** Ferramenta de build e servidor de desenvolvimento rápido para aplicações web modernas.
*   **TypeScript:** Superset do JavaScript que adiciona tipagem estática, melhorando a robustez do código.
*   **Tailwind CSS:** Framework CSS utilitário para estilização rápida e responsiva.
*   **react-calendar:** Componente React para exibição de calendários interativos.
*   **localStorage:** API do navegador para armazenamento de dados localmente.



## Estrutura do Projeto

O código-fonte está organizado da seguinte forma:

```
/home/ubuntu/calendario_menstrual/
├── public/             # Arquivos estáticos públicos
├── src/
│   ├── components/     # Componentes React reutilizáveis
│   │   ├── CalendarView.tsx
│   │   ├── CycleInfo.tsx
│   │   └── MenstruationForm.tsx
│   ├── lib/            # Funções utilitárias e lógica de negócio
│   │   └── cycleCalculator.ts # Lógica de cálculo do ciclo
│   ├── App.tsx         # Componente principal da aplicação
│   ├── index.css       # Estilos CSS globais (principalmente Tailwind)
│   └── main.tsx        # Ponto de entrada da aplicação React
├── .gitignore          # Arquivos e pastas ignorados pelo Git
├── index.html          # Arquivo HTML principal (template Vite)
├── package.json        # Metadados do projeto e dependências
├── pnpm-lock.yaml      # Arquivo de lock do gerenciador de pacotes pnpm
├── README.md           # Esta documentação
├── tailwind.config.js  # Configuração do Tailwind CSS
├── tsconfig.json       # Configuração principal do TypeScript
└── vite.config.ts      # Configuração do Vite
```

*   **`src/components`**: Contém os blocos de construção da interface: o calendário (`CalendarView`), o formulário de registro (`MenstruationForm`) e o painel de informações do ciclo (`CycleInfo`).
*   **`src/lib`**: Abriga a lógica principal de cálculo do ciclo menstrual e previsões (`cycleCalculator.ts`).
*   **`src/App.tsx`**: Orquestra os componentes, gerencia o estado principal (registros e previsões) e a interação com o `localStorage`.
*   **`src/main.tsx`**: Inicializa a aplicação React e a monta no DOM.



## Instalação e Configuração Local

Para executar o aplicativo localmente em seu ambiente de desenvolvimento, siga estas etapas:

1.  **Obtenha o Código:**
    *   Se você baixou o arquivo `.zip`, descompacte-o em um diretório de sua escolha.
    *   Se o código estiver em um repositório Git (por exemplo, após você enviá-lo para o seu GitHub), clone o repositório:
        ```bash
        git clone <URL_DO_SEU_REPOSITORIO>
        cd <NOME_DO_DIRETORIO>
        ```

2.  **Instale as Dependências:**
    Este projeto utiliza o `pnpm` como gerenciador de pacotes. Certifique-se de tê-lo instalado (você pode instalar via `npm install -g pnpm`). Em seguida, no diretório raiz do projeto, execute:
    ```bash
    pnpm install
    ```
    Este comando instalará todas as dependências listadas no `package.json`.

3.  **Execute o Servidor de Desenvolvimento:**
    Para iniciar o aplicativo em modo de desenvolvimento com hot-reloading, execute:
    ```bash
    pnpm run dev
    ```
    O aplicativo estará acessível em `http://localhost:5173` (ou outra porta, se a 5173 estiver ocupada).

4.  **Build para Produção:**
    Para criar uma versão otimizada para produção, execute:
    ```bash
    pnpm run build
    ```
    Os arquivos estáticos otimizados serão gerados no diretório `dist/`.



## Como Usar

1.  **Acesse o Aplicativo:** Abra o link fornecido (https://mdbafrcy.manus.space) ou execute localmente e acesse `http://localhost:5173`.
2.  **Registre sua Menstruação:**
    *   No formulário "Registrar Menstruação", selecione a **Data de Início** do seu último período menstrual usando o seletor de data.
    *   Insira a **Duração (dias)** do período (quantos dias a menstruação durou).
    *   Clique em "Salvar Registro".
3.  **Visualize no Calendário:**
    *   Após salvar um registro, os dias correspondentes à menstruação serão marcados em vermelho no calendário.
    *   Se você tiver registrado pelo menos dois ciclos, o calendário também exibirá:
        *   O **Período Fértil** estimado (marcado em azul).
        *   A data prevista para a **Próxima Menstruação** (marcada com uma borda roxa).
4.  **Consulte as Informações do Ciclo:**
    *   O painel "Informações do Ciclo" mostrará as datas estimadas para a janela fértil, o período de alta probabilidade de gravidez (que é um subconjunto da janela fértil) e a data da próxima menstruação, assim que houver dados suficientes (pelo menos dois ciclos registrados).
5.  **Continue Registrando:** Registre cada novo ciclo menstrual para melhorar a precisão das previsões ao longo do tempo.

**Importante:** Os dados são salvos apenas no seu navegador. Limpar os dados do site ou usar um navegador diferente resultará na perda dos registros anteriores.



## Lógica de Cálculo (Simplificada)

As previsões do ciclo são calculadas da seguinte forma:

1.  **Duração Média do Ciclo:** Calcula-se a média dos dias entre as datas de início das menstruações registradas (considerando ciclos entre 15 e 60 dias para evitar distorções por dados atípicos).
2.  **Próxima Menstruação:** Estima-se somando a duração média do ciclo à data de início da última menstruação registrada.
3.  **Dia Estimado da Ovulação:** Considera-se que a ovulação ocorre aproximadamente 14 dias *antes* do início da próxima menstruação estimada.
4.  **Janela Fértil:** Define-se como os 5 dias que antecedem o dia estimado da ovulação, mais o próprio dia da ovulação (total de 6 dias).
5.  **Janela de Alta Probabilidade:** Define-se como os 2 dias que antecedem o dia estimado da ovulação, mais o próprio dia da ovulação (total de 3 dias).

**Nota:** Estes são cálculos baseados em médias e métodos comuns de estimativa. A precisão aumenta com o número de ciclos registrados, mas variações individuais podem ocorrer. Este aplicativo não substitui aconselhamento médico profissional.

## Privacidade

Reforçamos que todos os dados inseridos (datas de início e durações) são armazenados **exclusivamente no `localStorage` do seu navegador**. Nenhuma informação é enviada para servidores externos. A privacidade dos seus dados é uma prioridade.

## Possíveis Melhorias Futuras

*   Adicionar opção para registrar sintomas ou notas diárias.
*   Implementar gráficos para visualizar a duração dos ciclos e períodos ao longo do tempo.
*   Oferecer opções de personalização (cores, temas).
*   Adicionar notificações (requereria uma abordagem diferente de armazenamento ou PWA).
*   Melhorar a lógica de cálculo para lidar com ciclos irregulares de forma mais sofisticada.
*   Internacionalização (suporte a outros idiomas).

