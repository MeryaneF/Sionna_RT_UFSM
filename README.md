# UFSM Sionna RT

Simulação do ambiente da UFSM utilizando o [Sionna RT](https://nvlabs.github.io/sionna/) em conjunto com ferramentas de modelagem e renderização 3D.

##  Objetivo: 

Este projeto tem como objetivo principal reproduzir virtualmente o ambiente da UFSM, utilizando o Sionna RT como motor de simulação.

## Tecnologias e Ferramentas

- [Blender 3.3](https://www.blender.org/download/releases/3-3/) – ferramenta principal de modelagem 3D
- [Blosm](https://github.com/eliemichel/MapsModelsImporter) – add-on para importação de mapas
- [Mitsuba](https://www.mitsuba-renderer.org/) – renderer usado para integração com o Sionna RT
- `.bat` customizado – utilizado para iniciar o Blender com suporte adequado ao Mitsuba (corrigindo incompatibilidades)

##  Como executar

1. Instale o [Blender 3.3](https://www.blender.org/download/releases/3-3/).
2. Adicione o Blosm e o Mitsuba como extensões.
3. Execute o script `.bat` incluído neste repositório para abrir o Blender com o ambiente configurado.
4. Importe os modelos da UFSM e inicie a simulação no Sionna RT.
4. Importe os modelos da UFSM no Blender:
   - Utilize o add-on Blosm para importar a estrutura da UFSM diretamente no Blender.
   - Durante a importação, ative a opção para importar somente os elementos “Building”, evitando objetos desnecessários.
   - Evite importar como um único bloco os modelos devem vir separados para facilitar o mapeamento dos materiais e ajustes individuais.
   - Após a importação, renomeie os materiais dos objetos para que correspondam exatamente aos nomes dos materiais de rádio definidos no Sionna RT. Isso garante que o simulador                interprete corretamente as propriedades eletromagnéticas de cada superfície.
   - Acesse as configurações de World no Blender e altere os parâmetros conforme os requisitos do Sionna RT (como tipo de iluminação, ambiente HDRI, visibilidade do fundo etc.).
  
##  Código
   - Na pasta simulações há o código em que eu usei com a cena gerada no blender já configurada com objetos do tipo `itu_concrete`
## Sites Úteis
1. Sionna Tutorial: https://nvlabs.github.io/sionna/rt/index.html
2. Tutorial Blender: https://youtu.be/7xHLDxUaQ7c?si=Ogl_WLvEYFHjhle1
