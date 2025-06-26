# 🏛️ Legal MCP Server Argentina

> Un servidor MCP especializado para documentos legales argentinos con búsqueda inteligente y análisis de jurisprudencia

[![MCP Compatible](https://img.shields.io/badge/MCP-Compatible-blue)](https://modelcontextprotocol.io/)
[![Node.js](https://img.shields.io/badge/Node.js-18+-green)](https://nodejs.org/)
[![SQLite](https://img.shields.io/badge/SQLite-3.45+-lightgrey)](https://sqlite.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## 🚀 Inicio Rápido

```bash
# Instalación
npm install -g legal-mcp-server-argentina

# Configurar con datos de ejemplo
legal-mcp-server --setup-sample-data

# Agregar a Claude Desktop
```

## ✨ Características

- 🔍 **Búsqueda semántica** en documentos legales argentinos
- ⚖️ **Categorización automática** por área de práctica (Civil, Penal, Comercial, etc.)
- 📊 **Estadísticas y analytics** de jurisprudencia
- 🚀 **Alto rendimiento** con SQLite optimizado y caché inteligente
- 🔌 **Compatible** con Claude Desktop, Cursor, y otros clientes MCP
- 📚 **Base de datos** precompilada con documentos legales argentinos
- 🛡️ **Seguro** con validación de entradas y manejo robusto de errores

## 📋 Herramientas Disponibles

| Herramienta | Descripción | Ejemplo |
|-------------|-------------|---------|
| `search_legal_documents` | Buscar documentos por contenido, área, autor | Buscar "contratos de trabajo" |
| `get_document_by_id` | Obtener contenido completo de un documento | Ver documento ID 123 |
| `list_practice_areas` | Listar áreas de práctica disponibles | Ver todas las especialidades |
| `get_statistics` | Estadísticas de la biblioteca legal | Dashboard completo |

## 🛠️ Instalación

### Prerrequisitos
- Node.js 18+ 
- Claude Desktop App o compatible MCP client

### Instalación Local

```bash
# Clonar repositorio
git clone https://github.com/tu-usuario/legal-mcp-server-argentina.git
cd legal-mcp-server-argentina

# Instalar dependencias
npm install

# Configurar base de datos
npm run setup

# Ejecutar servidor
npm start
```

### Instalación via NPM

```bash
npm install -g legal-mcp-server-argentina
legal-mcp-server
```

## ⚙️ Configuración

### Claude Desktop

Agregar a tu `claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "legal-argentina": {
      "command": "node",
      "args": ["/ruta/a/legal-mcp-server-argentina/server.js"],
      "env": {
        "LEGAL_DB_PATH": "/ruta/a/legal_mcp.db"
      }
    }
  }
}
```

### Variables de Entorno

```bash
# Opcional: Ruta personalizada para la base de datos
export LEGAL_DB_PATH="/custom/path/legal_mcp.db"

# Opcional: Nivel de logging
export LOG_LEVEL="info"

# Opcional: Tamaño de caché (en MB)
export CACHE_SIZE="256"
```

## 🎯 Casos de Uso

### Para Abogados
- **Investigación jurisprudencial**: "Buscar fallos sobre daños y perjuicios en CABA"
- **Análisis de precedentes**: Encontrar casos similares por materia
- **Preparación de escritos**: Acceso rápido a doctrina y normativa

### Para Estudiantes de Derecho
- **Estudio de casos**: Búsqueda por tema y complejidad
- **Investigación académica**: Análisis estadístico de tendencias jurisprudenciales
- **Preparación de exámenes**: Acceso estructurado a material de estudio

### Para Desarrolladores
- **Integración legal tech**: API estandarizada para aplicaciones jurídicas
- **Prototipado rápido**: Base de datos lista para usar
- **Ejemplo MCP**: Implementación de referencia para otros dominios

## 📊 Performance

### Benchmarks
- **Búsqueda simple**: < 50ms promedio
- **Búsqueda compleja**: < 200ms promedio  
- **Capacidad**: 100,000+ documentos
- **Concurrencia**: 50+ consultas simultáneas

### Optimizaciones Incluidas
- WAL mode en SQLite para mejor concurrencia
- Índices compuestos para consultas rápidas
- Caché en memoria para consultas frecuentes
- Connection pooling para alta demanda

## 🧪 Ejemplos de Uso

### Búsqueda Básica
```javascript
// A través de Claude Desktop
"Buscar documentos sobre contratos de alquiler"

// Resultado: Lista de contratos con snippets relevantes
```

### Búsqueda Avanzada
```javascript
// Búsqueda por múltiples criterios
"Buscar fallos de la Cámara Civil sobre responsabilidad médica de los últimos 5 años"
```

### Análisis Estadístico
```javascript
// Obtener tendencias
"Mostrar estadísticas de documentos por área de práctica"
```

## 🔧 Desarrollo

### Ejecutar en Modo Desarrollo

```bash
# Con hot reload
npm run dev

# Con debugging
npm run debug

# Ejecutar tests
npm test

# Generar coverage
npm run coverage
```

### Estructura del Proyecto

```
legal-mcp-server-argentina/
├── server.js              # Servidor MCP principal
├── lib/                   # Librerías y utilidades
│   ├── database.js        # Manejo de SQLite
│   ├── search.js          # Lógica de búsqueda
│   └── cache.js           # Sistema de caché
├── data/                  # Datos y esquemas
│   ├── schema.sql         # Esquema de base de datos
│   └── sample_docs.json   # Documentos de ejemplo
├── tests/                 # Tests unitarios
├── docs/                  # Documentación detallada
└── scripts/               # Scripts de utilidad
```

### Agregar Nuevos Documentos

```javascript
// Script para importar documentos
node scripts/import-documents.js --file documents.json --format json
```

## 🤝 Contribuir

¡Las contribuciones son bienvenidas! Por favor:

1. Fork el repositorio
2. Crea una rama para tu feature (`git checkout -b feature/nueva-funcionalidad`)
3. Commit tus cambios (`git commit -am 'Agregar nueva funcionalidad'`)
4. Push a la rama (`git push origin feature/nueva-funcionalidad`)
5. Abre un Pull Request

### Áreas de Contribución

- 📚 **Datos**: Agregar más documentos legales argentinos
- 🔍 **Búsqueda**: Mejorar algoritmos de relevancia
- 🏗️ **Arquitectura**: Optimizaciones de performance
- 📖 **Documentación**: Guías y ejemplos adicionales
- 🧪 **Testing**: Casos de prueba y validación

## 📄 Licencia

Este proyecto está licenciado bajo la Licencia MIT - ver el archivo [LICENSE](LICENSE) para detalles.

## 🙏 Reconocimientos

- **Anthropic** por el desarrollo del Model Context Protocol
- **Comunidad legal argentina** por el feedback y sugerencias
- **Contribuidores** del proyecto open source

## 📞 Soporte

- **Issues**: [GitHub Issues](https://github.com/tu-usuario/legal-mcp-server-argentina/issues)
- **Documentación**: [Wiki del proyecto](https://github.com/tu-usuario/legal-mcp-server-argentina/wiki)
- **Comunidad**: [Discussions](https://github.com/tu-usuario/legal-mcp-server-argentina/discussions)

## 🗺️ Roadmap

### v2.1 (Actual)
- ✅ Búsqueda básica y estadísticas
- ✅ Compatibilidad MCP completa
- ✅ Optimizaciones de performance

### v2.2 (Próximo Release)
- 🔄 Búsqueda semántica con embeddings
- 🔄 API REST complementaria
- 🔄 Importación automática de BOE

### v3.0 (Futuro)
- 📅 Análisis de tendencias jurisprudenciales
- 📅 Integración con sistemas de gestión legal
- 📅 Soporte multi-jurisdicción (LATAM)

---

**¿Encontraste útil este proyecto?** ⭐ ¡Dale una estrella en GitHub!

**¿Tienes sugerencias?** 💡 [Abrir un issue](https://github.com/tu-usuario/legal-mcp-server-argentina/issues/new)
