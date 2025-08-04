# GlowSkin Angular - Website Estética

Sitio web para GlowSkin, clínica de estética facial desarrollado en Angular, con Server-Side Rendering (SSR) y prerenderizado optimizado para SEO.

## 💡 La Historia Detrás del Proyecto

Como ingenieros y desarrolladores, a veces damos más espacio a los proyectos de empresas que a proyectos propios. 

Me ha gustado poder apoyar a mi esposa en este proyecto, por eso en estas semanas he estado dedicando gran parte de mi tiempo libre en encontrar las mejores maneras de hacerle marketing a su empresa **#GlowSkinBq** con tecnología.

Lo cual ha traído un sinnúmero de nuevos aprendizajes en un lado de la industria que no solemos tocar como el marketing, el SEO, el web scraping, las plataformas de publicidad y CRMs.

### ¿Qué hicimos?

A simple vista es una página web normal.

Pero tiene todo el potencial para ser un proyecto robusto y escalable en el tiempo, **100% con IA**. Todo en base a mi conocimiento de la industria del software.

**Características técnicas destacadas:**

- ⚡ **Desarrollado en Angular 17** con las últimas características del framework
- 🧩 **Componentes separados** siguiendo el principio de responsabilidad única
- 🚀 **Server Side Rendering (SSR)** y prerenderizado activado para configuración de SEO a través de AWS Lambda
- ⚖️ **Funciones híbridas** del lado del cliente y otras del lado del servidor
- 🔄 **Flujo simple de CI/CD** con branch de producción y pruebas
- ☁️ **Hospedado en Amazon Amplify** (similar a usar S3 y CloudFront)
- 🌐 **Dominio personalizado** con Route 53
- 📦 **Repositorio de Assets separado** para reducir tiempos de compilación y sobrecarga del sitio (muy útil cuando se compila en la nube de AWS)
- 🔍 **SEO optimizado** con palabras clave para su nicho de negocio
- 🕷️ **Web Scraping** para obtener reviews de Google (pendiente de probar el API oficial)

**¿Por qué es especial este proyecto?**

Es de **código abierto** y lo pueden utilizar de guía para cualquier proyecto similar que tengan en mente. Combina las mejores prácticas de desarrollo moderno con estrategias de marketing digital, creando una solución integral que va más allá de una simple página web.

## 🚀 Tecnologías

- **Angular 17** - Framework principal
- **Server-Side Rendering (SSR)** - Para mejor SEO y rendimiento
- **Prerenderizado** - Páginas pre-generadas
- **Tailwind CSS** - Estilos
- **AWS Amplify** - Deployment y hosting

## 📁 Estructura del Proyecto

```
src/
├── app/
│   ├── components/     # Componentes reutilizables
│   ├── pages/         # Páginas principales
│   └── services/      # Servicios y APIs
├── assets/
│   ├── images/        # Imágenes optimizadas
│   └── data/          # Datos JSON
└── styles/            # Estilos globales
```

## 🛠️ Comandos de Desarrollo

### Desarrollo Local

```bash
# Instalar dependencias
npm install

# Servidor de desarrollo
npm start
# o
ng serve

# Servidor de desarrollo con SSR
npm run serve:ssr
```

### Build y Compilación

```bash
# Build estándar (SPA)
npm run build

# Build con SSR
npm run build:ssr

# Build con prerenderizado (recomendado para producción)
npm run build:prerender

# Solo prerenderizado
npm run prerender
```

### Testing

```bash
# Tests unitarios
npm test

# Tests con coverage
ng test --code-coverage
```

## 🌐 Server-Side Rendering (SSR)

### ¿Qué es SSR?

- **Mejor SEO**: Los motores de búsqueda pueden indexar el contenido
- **Mejor rendimiento**: Carga inicial más rápida
- **Mejor UX**: Contenido visible inmediatamente

### Configuración SSR

- **Entry point**: `src/main.server.ts`
- **Server**: `server.ts` (Express.js)
- **Prerenderizado**: Páginas pre-generadas en build time

### Rutas Prerenderizadas

```javascript
// prerender.config.js
[
  "/", // Home
  "/nosotros", // Sobre nosotros
  "/precios", // Precios y servicios
  "/blog", // Blog
  "/casos-reales", // Casos de éxito
  "/agendar", // Agendar cita
  "/confirmacion-pago", // Confirmación
];
```

## 🚀 Deployment en AWS Amplify

### Configuración Automática

El proyecto incluye la configuración optimizada para Amplify:

- **`amplify.yml`** - Configuración principal para build y prerenderizado

### Pasos para Deployment

1. **Conectar repositorio en Amplify Console**
2. **Configurar build settings**:
   ```yaml
   Build image: Amazon Linux:2023
   Build commands: amplify.yml
   ```
3. **Variables de entorno** (opcional):
   ```
   NODE_ENV=production
   PORT=3000
   ```

### Estructura de Build

```
dist/glow-skin-angular/
├── browser/          # Archivos del cliente
├── server/           # Archivos del servidor SSR
└── prerender/        # Páginas prerenderizadas
```

## 📊 Optimizaciones Implementadas

### Performance

- ✅ **Lazy loading** de módulos
- ✅ **Image optimization** con WebP
- ✅ **Cache headers** optimizados
- ✅ **Compression** automática

### SEO

- ✅ **Meta tags** dinámicos
- ✅ **Structured data** (JSON-LD)
- ✅ **Sitemap** automático
- ✅ **Prerenderizado** de páginas principales

### Caching

- ✅ **Browser cache** para assets estáticos
- ✅ **Build cache** para node_modules
- ✅ **Angular cache** para builds más rápidos

## 🔧 Scripts Disponibles

| Comando                   | Descripción               |
| ------------------------- | ------------------------- |
| `npm start`               | Servidor de desarrollo    |
| `npm run build`           | Build estándar            |
| `npm run build:ssr`       | Build con SSR             |
| `npm run build:prerender` | Build + prerenderizado    |
| `npm run prerender`       | Solo prerenderizado       |
| `npm run serve:ssr`       | Servir SSR localmente     |
| `npm test`                | Tests unitarios           |
| `npm run scrape-reviews`  | Scraper de Google Reviews |

## 📱 Páginas Principales

- **Home** (`/`) - Landing page principal
- **Nosotros** (`/nosotros`) - Información de la clínica
- **Precios** (`/precios`) - Servicios y tarifas
- **Blog** (`/blog`) - Artículos y consejos
- **Casos Reales** (`/casos-reales`) - Resultados de pacientes
- **Agendar** (`/agendar`) - Reserva de citas

## 🎨 Componentes Principales

- **Header** - Navegación principal
- **Carousel** - Galería de imágenes
- **Google Reviews** - Reseñas de Google
- **WhatsApp Widget** - Chat flotante
- **Footer** - Información de contacto

## ✅ Estado de las Pruebas

### Build Tests ✅

- **Build estándar**: ✅ Funcionando
- **Build SSR**: ✅ Funcionando
- **Build prerenderizado**: ✅ Funcionando
- **Budgets CSS**: ✅ Ajustados (6kb warning, 8kb error)

### SSR Tests ✅

- **Servidor SSR**: ✅ Funcionando en puerto 4000
- **Prerenderizado**: ✅ 6 rutas generadas
- **Archivos estáticos**: ✅ Servidos correctamente

### Estructura de Archivos ✅

```
dist/glow-skin-angular/
├── browser/
│   ├── index.html          # Home prerenderizada
│   ├── nosotros/index.html # Nosotros prerenderizada
│   ├── precios/index.html  # Precios prerenderizada
│   ├── blog/index.html     # Blog prerenderizada
│   ├── casos-reales/index.html # Casos prerenderizada
│   └── assets/             # Assets optimizados
├── server/
│   ├── server.mjs          # Servidor Express SSR
│   ├── main.server.mjs     # Entry point SSR
│   └── polyfills.server.mjs # Polyfills servidor
└── prerendered-routes.json # Lista de rutas prerenderizadas
```

## 🔍 Troubleshooting

### Build Fails

1. Verificar dependencias: `npm ci`
2. Limpiar cache: `rm -rf .angular/cache`
3. Rebuild: `npm run build:prerender`

### SSR Issues

1. Verificar `server.ts` está configurado
2. Comprobar `main.server.ts` existe
3. Revisar logs en Amplify Console

### Performance Issues

1. Optimizar imágenes con WebP
2. Implementar lazy loading
3. Revisar bundle size con `ng build --stats-json`

## 📚 Recursos Adicionales

- [Angular SSR Documentation](https://angular.io/guide/ssr)
- [AWS Amplify Documentation](https://docs.aws.amazon.com/amplify/)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)

## 🤝 Contribución

1. Fork el proyecto
2. Crear feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit cambios (`git commit -m 'Add some AmazingFeature'`)
4. Push al branch (`git push origin feature/AmazingFeature`)
5. Abrir Pull Request

## 📄 Licencia

Este proyecto es de **código abierto** y puede ser copiado, modificado y reproducido libremente.

**⚠️ Importante:** El nombre "GlowSkin" y la marca "#GlowSkinBq" son de uso privado. Si deseas utilizar este proyecto como base para tu propio negocio, debes:

- ✅ Cambiar el nombre de la empresa/marca
- ✅ Modificar el contenido específico de GlowSkin
- ✅ Actualizar las imágenes y assets propios
- ✅ Cambiar la información de contacto y ubicación

**Siéntete libre de usar este código como plantilla para tu proyecto de estética, spa, clínica o cualquier negocio similar.**
