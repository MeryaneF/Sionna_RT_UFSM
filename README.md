# Tutorial: Conversão de Dados OSM para Sionna RT (Cena 3D)

Este tutorial guia você através do processo de conversão de dados OpenStreetMap (OSM) para um modelo 3D compatível com o Sionna RT.

## 📋 Pré-requisitos
- Java JDK 8+ instalado
- Osm2World (versão 0.4.0 ou superior)
- Blender (para visualização/edição opcional)
-  **Atenção:** Todos os comandos devem ser executados no PowerShell ou CMD como Administrador

## 🌐 Passo 1: Obtenção dos Dados OSM
1. Acesse [BBBike Extract](https://extract.bbbike.org/)
2. Selecione a área desejada:
   - Defina o polígono de extração
   - Escolha formato `.osm`
3. Faça o download e aguarde o e-mail com os dados

## ⚙️ Passo 2: Configuração do Ambiente
### Verificação do Java

```
java -version
```

## Caso não tenha Java instalado:

Baixe o JDK mais recente Oracle JDK ou OpenJDK

Adicione ao PATH:
C:\Program Files\Java\jdk-[version]\bin
Instalação do Osm2World
Baixe a versão mais recente em osm2world.org
Extraia o arquivo ZIP (ex.: C:\OSM2World-0.4.0-bin)

🛠️ Passo 3: Pré-processamento dos Dados
 Crie uma pasta de projeto:
```
mkdir C:\OSM_Project
cd C:\OSM_Project

```
📂Copie para esta pasta:
Arquivo OSM (ex.: ufsm.osm)
Pasta do Osm2World

⚙️ Configuração do Osm2World
Edite o arquivo:
OSM2World-0.4.0-bin\config\standard.properties

Adicione/altere:
```
ignoreInvalidGeometry=true
generateSports=false
generateTrees=false
generatePowerLines=false
minBuildingHeight=3.0
buildingHeight=10.0
```
🖥️ Passo 4: Conversão para 3D
Execute no diretório do projeto:
```
java -Xmx8G -cp "OSM2World-0.4.0-bin\Osm2World.jar;OSM2World-0.4.0-bin\lib\*" org.osm2world.console.OSM2World --input ufsm.osm --output ufsm.obj --config OSM2World-0.4.0-bin\config\standard.properties
Possíveis Erros (podem ser ignorados):
"Degenerate triangle"
"Index: -1"
"Wall boundaries"
```
✅ Verificação
```
dir ufsm.obj
Arquivo deve existir e ter >1MB
```
🎨 Passo 5: Visualização no Blender
Abra o Blender
File → Import → Wavefront (.obj)
Selecione ufsm.obj
Otimizações (opcional):
Aplicar modificador "Decimate"
Remover objetos problemáticos
Exportar para .glTF ou .fbx

📂 Estrutura do Projeto
```
/projeto
├── /OSM2World-0.4.0-bin    # Ferramenta de conversão
├── /config                 # Configurações personalizadas
├── input.osm               # Dados OSM originais
└── output.obj              # Modelo 3D gerado
```
⚠️ Troubleshooting
Problemas com Java: 
Verifique java -version e PATH
Arquivo .obj vazio: Verifique logs de erro e tamanho do arquivo OSM
Texturas ausentes: Osm2World gera apenas geometria básica

📚 Recursos Adicionais
Documentação Osm2World - https://osm2world.org/docs/
Sionna RT Documentation - https://nvlabs.github.io/sionna/rt/index.html
