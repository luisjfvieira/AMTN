# AMTN - Mapa Interativo de Telheiras Norte

Uma plataforma de mapa interativo para visualizar as áreas de influência da Associação de Moradores de Telheiras Norte (AMTN), em Lisboa.

## 🗺️ Características

- **Mapa Interativo**: Visualização das áreas de influência em tempo real
- **Múltiplas Camadas**: Suporte para vários polígonos de áreas
- **Design Responsivo**: Funciona em desktop, tablet e mobile
- **Controles Intuitivos**: Zoom, pan, e navegação fácil
- **Popup de Informações**: Detalhes de cada zona ao clicar

## 🚀 Começar

### Abrir o Mapa

Basta abrir o ficheiro `index.html` num navegador web ou aceder à versão online.

### Requisitos

Apenas um navegador web moderno (Chrome, Firefox, Safari, Edge).

## 📦 Estrutura do Projeto

```
AMTN/
├── index.html            # Página principal do mapa
├── area_layers.geojson   # Áreas de influência da AMTN (2 polígonos)
├── telheiras_norte.osm   # Extracto OSM em bruto da área do Polígono 1
├── osm/                  # O mesmo extracto dividido por tema (GeoJSON)
│   ├── edificios.geojson
│   ├── vias.geojson
│   ├── pedonal_ciclavel.geojson
│   ├── verde.geojson
│   ├── transportes.geojson
│   ├── poi.geojson
│   ├── arvores.geojson
│   └── outros.geojson
├── README.md             # Este ficheiro
└── .gitignore            # Ficheiros ignorados pelo Git
```

## 🛠️ Tecnologias Utilizadas

- **Leaflet**: Biblioteca de mapas JavaScript de código aberto
- **OpenStreetMap**: Dados cartográficos
- **GeoJSON**: Formato de dados geográficos

## 📝 Dados

Os dados das áreas de influência foram convertidos do formato KML para GeoJSON para melhor compatibilidade com aplicações web.

### Ficheiro: `area_layers.geojson`

Contém dois polígonos representando as áreas de influência:
- **Polígono 1**: Zona norte
- **Polígono 2**: Zona sul/central

Coordenadas: Lisboa, Portugal (~38.76°N, 9.17°W)

### Extracto OpenStreetMap: `telheiras_norte.osm`

Extracto completo do OpenStreetMap recortado pela área do **Polígono 1** (0,367 km²),
obtido através da Overpass API. Contém 410 *ways*, 2130 *nodes* e 625 elementos com
etiquetas, em XML OSM com metadados — abre directamente no JOSM e no QGIS.

As geometrias que atravessam o limite do polígono (ruas, uma linha eléctrica) são
mantidas na íntegra, para não partir a topologia. As relações de percurso
(carreiras de autocarro, itinerários rodoviários) **não** são expandidas: várias
delas atravessam o país inteiro e arrastariam consigo meio Portugal.

### Camadas temáticas: `osm/`

O mesmo extracto convertido para GeoJSON e dividido por tema, para poder ser
carregado e alternado no mapa. Cada camada é descarregada apenas quando é activada,
para manter o arranque da página rápido (~297 KB no total).

Para actualizar os dados, repetir a consulta Overpass e voltar a dividir por tema.

## 🎨 Personalização

Pode editar o ficheiro `index.html` para:
- Mudar as cores dos polígonos (variável `colors`)
- Ajustar o zoom inicial (método `map.setView()`)
- Adicionar mais camadas de dados
- Personalizar o estilo

## 🤝 Contribuindo

Para sugerir melhorias ou reportar problemas:
1. Faça um fork deste repositório
2. Crie uma branch para a sua funcionalidade
3. Submeta um pull request

## 📄 Licença

Este projeto é aberto para uso pela comunidade AMTN.

## 📧 Contacto

Para questões sobre o projeto, contacte a AMTN.

---

**Desenvolvido para AMTN - Associação de Moradores de Telheiras Norte**
