# ¿Cómo voto? (29N)

**El proceso electoral, explicado.**

> Herramienta experimental. No es un servicio oficial.
>
> **Publicada en:** https://build.barraca.house/punto-atencion-ciudadana/como-voto-b

**¿Cómo voto?** es una guía para entender las elecciones generales del 29-N sin ruido: qué hay que hacer para votar en cada situación, qué plazos corren y qué página oficial sostiene cada dato. Habla de procedimientos, no de candidaturas, programas ni encuestas, y no recomienda el voto.

La herramienta forma parte de **Punto de Atención Ciudadana**, la plataforma que seis equipos construimos en el **Build night BARRACA x SOTI** del 22 de octubre de 2026 en Flywire, València. Nos tocó el track **¿Cómo voto?** y este es el resultado de la noche: una guía navegable, un simulador y una mascota que responde dudas con fuentes oficiales delante.

## Qué encontrarás

- **[Cómo votar, caso por caso](https://build.barraca.house/punto-atencion-ciudadana/como-voto-b/como-votar)**. En persona, por correo, desde el extranjero (CERA), temporalmente fuera (ERTA), con apoyo o en Braille, y qué hacer si te surgen dudas el día de la votación. Cada caso con sus pasos, sus fechas y su fuente.
- **[Lo que se dice sobre votar, frente a la ley](https://build.barraca.house/punto-atencion-ciudadana/como-voto-b/bulos)**. Voto en blanco, nulo y abstención, papeletas tachadas o voto por correo: cada bulo habitual con el artículo de la LOREG que lo contradice.
- **[El recorrido del voto](https://build.barraca.house/punto-atencion-ciudadana/como-voto-b/escrutinio)**. Qué pasa al cerrar el colegio: del recuento en la mesa a los resultados oficiales en el BOE, paso a paso y artículo a artículo.
- **[La ley D'Hondt, explicada](https://build.barraca.house/punto-atencion-ciudadana/como-voto-b/escanos)**. La fórmula, la barrera del 3 %, la tabla de cocientes y un simulador para cambiar votos y ver cómo se reparten los escaños. Incluye los resultados oficiales de 2023 y escenarios con otras reglas.
- **[Del hemiciclo a cada provincia](https://build.barraca.house/punto-atencion-ciudadana/como-voto-b/mapa)**. Cómo quedó el Congreso en 2023, de dónde sale cada escaño y un hemiciclo en 3D para explorarlo provincia a provincia.
- **Votón**. La mascota que enlaza todas las piezas y el chat que responde dudas en cualquier página. Contesta en castellano llano, con pasos numerados y la fuente oficial debajo; si no puede confirmarlo, lo dice y enlaza la sede oficial.

## Cómo se hizo

Una noche, tres horas y media, risas y cervezas. La plataforma reunía seis funcionalidades para hacer sencillo lo que la Administración hace difícil:

- un buscador de ayudas;
- un traductor de documentos, de enrevesado a sencillo;
- un verificador de mensajes y enlaces para evitar fraudes y estafas;
- un asistente de trámites;
- una guía para las elecciones del 29-N, que es esta;
- una herramienta para comprobar el cumplimiento de promesas electorales.

Nosotros nos quedamos con la guía electoral. Partimos del marco de conocimiento del track, contrastamos los procedimientos con la Junta Electoral Central, el INE, Correos, el BOE y el Ministerio del Interior, y montamos encima las piezas interactivas: el recorrido del voto, los bulos, el escrutinio, el simulador de D'Hondt y el mapa. Votón y el chat llegaron después, para que ninguna duda se quedara sin salida.

Todo el contenido está escrito para leerse sin conocimientos previos y cada respuesta enlaza la página concreta que la sostiene. La herramienta no inventa plazos, importes ni requisitos: cuando no puede confirmar algo, lo dice.

**This is the REAL BARRACA.**

## Dónde verlo

- **La herramienta:** https://build.barraca.house/punto-atencion-ciudadana/como-voto-b
- **La plataforma completa:** https://build.barraca.house/punto-atencion-ciudadana/
- **El repositorio original**, archivado en solo lectura por la organización: https://github.com/barracafh/build-como-voto-b
- **Este fork**, con la documentación y los créditos del equipo: https://github.com/lruicas/build-como-voto-b

El chat funciona con las claves del evento hasta el **30 de noviembre de 2026**. Después, la guía, el simulador y el mapa siguen disponibles, pero las respuestas de Votón necesitan una clave propia.

## Equipo

**SERVING COUNT(\*)** — track ¿Cómo voto?:

- Claudia Ruiz García ([@clauu-uni](https://github.com/clauu-uni))
- Javier Martínez Llinares ([@Jamarlli](https://github.com/Jamarlli))
- Pedro de Luna Huerta ([@Pedrodeluna](https://github.com/Pedrodeluna))
- Pablo Santana ([@NegativeAlpha88](https://github.com/NegativeAlpha88))
- Lara Ruiz Casado ([@lruicas](https://github.com/lruicas))

El código se publicó en el repositorio del evento, que quedó archivado en solo lectura y no permite pull requests. Este fork existe para poder continuar el proyecto y dejar por escrito quién lo hizo. Las contribuciones de esta copia se pueden consultar en [la gráfica del repositorio](https://github.com/lruicas/build-como-voto-b/graphs/contributors).

## Cómo está montado

Next.js 16 (App Router) y React 19, con Tailwind CSS 4, componentes de shadcn/ui sobre Base UI, Three.js para el hemiciclo y Bun como gestor de paquetes. La IA se llama solo desde el servidor (HelmCode, compatible con la API de OpenAI) y nunca desde el navegador.

Con Bun y Node 22 o superior:

```sh
bun install --frozen-lockfile
bun run dev
```

La app queda en `http://localhost:3000/punto-atencion-ciudadana/como-voto-b`. Para comprobar que compila:

```sh
bun run build
```

Para el chat en local hacen falta `HELMCODE_API_KEY` y `HELMCODE_MODEL` en `.env.local`; `FACTCHECK_API_KEY` es opcional. Las claves no se suben al repositorio ni llevan el prefijo `NEXT_PUBLIC_`.

El contenido vive en `contexto.md` y `src/datos/`; los textos de cada pieza, en `src/app/`. Las reglas de diseño y las de la plataforma están en [AGENTS.md](AGENTS.md), y el reto del track, en [SETUP.md](SETUP.md). El diseño parte de Sol, el sistema visual de Reforma Digital: el origen y la licencia están en [AVISO.md](AVISO.md).

## Datos, fuentes y privacidad

- La ficha declara `datos: simulados`. Los resultados de 2023 proceden de datos públicos del Ministerio del Interior (Infoelectoral).
- Fuentes citadas en la herramienta: Junta Electoral Central, INE (Oficina del Censo Electoral), Correos, BOE (LOREG y Real Decreto de convocatoria) e Infoelectoral.
- No se recoge ni se guarda lo que escribe el ciudadano: ni base de datos, ni logs con su texto. El historial de la conversación vive solo en el navegador durante la sesión.
- El chat tiene una batería de 458 casos en `pruebas/banco-*.json` (contenido, preguntas adversarias, fechas y bulos). Se lanza con `bun pruebas/evaluar.mjs` y respeta los límites de peticiones del servidor.
- No se habla de partidos, candidaturas ni encuestas, y no se recomienda el voto.

## Qué falta para producción

Esto es el código tal como quedó tras la noche. Para convertirlo en un servicio público de verdad faltaría:

- **Claves y coste propios.** La IA del evento caduca el 30 de noviembre de 2026; haría falta una cuenta y un presupuesto de modelo sostenibles.
- **Revalidar el calendario.** Plazos, supuestos y enlaces están atados al 29-N de 2026. Para otra convocatoria hay que actualizar fechas, fuentes y la ficha antes de publicar.
- **Revisión editorial y legal.** Contrastar cada dato con la versión vigente de la LOREG y del calendario de la JEC, y revisar el aviso de no oficialidad y la política de privacidad.
- **Accesibilidad con personas usuarias.** Hay enlace de salto, foco visible, contraste y movimiento reducido, pero falta una auditoría real con lectores de pantalla y pruebas con personas con discapacidad.
- **Más pruebas del chat.** La batería actual acierta entre el 90 % y el 94 %; antes de producción convendría ampliarla y medir también latencia y coste.
- **Dominio y despliegue propios.** Ahora vive en `build.barraca.house`; un servicio real necesitaría su dominio, su analítica mínima y su plan de mantenimiento.

## Licencia

MIT. El detalle del diseño de partida y su licencia están en [AVISO.md](AVISO.md) y [LICENSE](LICENSE).
