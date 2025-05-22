# Tutorial: Conversão de Dados OSM para Sionna RT (Cena 3D)

Este tutorial guia você através do processo de conversão de dados OpenStreetMap (OSM) para um modelo 3D compatível com o Sionna RT.

## 📋 Pré-requisitos
- Java JDK 8+ instalado
- Osm2World (versão 0.4.0 ou superior)
- Blender (para visualização/edição opcional)
- ~8GB de RAM disponível

## 🌐 Passo 1: Obtenção dos Dados OSM
1. Acesse [BBBike Extract](https://extract.bbbike.org/)
2. Selecione a área desejada:
   - Defina o polígono de extração
   - Escolha formato `.osm`
3. Faça o download e aguarde o e-mail com os dados

## ⚙️ Passo 2: Configuração do Ambiente
### Verificação do Java
```cmd
java -version
