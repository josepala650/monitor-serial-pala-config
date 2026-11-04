# monitor-serial-pala-config
Configuración de videos y publicidad de Monitor Serial PALA
Monitor Serial PALA — configuración de videos y publicidad
Este repositorio contiene la configuración remota que consulta Monitor Serial PALA. La aplicación lee publicidad.json desde GitHub; para cambiar los videos no hace falta modificar Python ni volver a compilar el Snap.
Archivo que se debe editar
El archivo principal es publicidad.json. Para modificar la lista de YouTube, editá los valores playlist_id y video_inicial.

Ejemplo de enlace completo de YouTube:
https://www.youtube.com/watch?v=j2guSepUVq8&list=PLKILNCx3VtD6ceqXvEs0wyJg-XsFbelF1
De ese enlace se extraen:
- video_inicial: el texto que aparece después de v= y antes de &.
- playlist_id: el texto que aparece después de list=.
Para la lista inicial de Tutoriales JEP, el archivo publicidad.json debe contener:
{
  "version": 1,
  "activo": true,
  "tipo": "playlist",
  "playlist_id": "PLKILNCx3VtD6ceqXvEs0wyJg-XsFbelF1",
  "video_inicial": "j2guSepUVq8",
  "espera_inicio_segundos": 300,
  "reproduccion_automatica": true,
  "reproduccion_continua": true,
  "permitir_ventana_independiente": true
}
Cómo cambiar la lista
1. Abrí el repositorio monitor-serial-pala-config en GitHub.
2. Abrí publicidad.json y presioná el lápiz (Edit this file).
3. Copiá el enlace de la nueva lista de reproducción.
4. Reemplazá playlist_id por el valor que sigue a list=.
5. Reemplazá video_inicial por el valor que sigue a v=.
6. Presioná Commit changes para guardar.
No pegues el enlace completo en esos campos: cada uno debe contener solamente su identificador.
Activar o desactivar el espacio promocional
- Para habilitarlo: "activo": true
- Para deshabilitarlo: "activo": false
Tiempo de espera
espera_inicio_segundos está expresado en segundos:
- 300 = 5 minutos.
- 600 = 10 minutos.
- 900 = 15 minutos.
Reproducción
- reproduccion_automatica: solicita iniciar la reproducción automáticamente cuando se habilita el reproductor. El navegador/YouTube puede impedir el inicio automático con sonido; en ese caso el usuario deberá iniciar la reproducción manualmente.
- reproduccion_continua: indica que se utilizará la lista como reproducción continua.
- permitir_ventana_independiente: habilita la opción de abrir el contenido en una ventana separada, si la versión instalada de Monitor Serial PALA ofrece ese control.
Dirección directa del archivo
La aplicación debe consultar la versión raw del archivo, no la página HTML de GitHub:
https://raw.githubusercontent.com/josepala650/monitor-serial-pala-config/main/publicidad.json
Reglas importantes
- publicidad.json debe ser JSON válido. No agregues comentarios // ni /* ... */ dentro del archivo.
- Conservá las comillas dobles en nombres y valores de texto.
- No publiques tokens, contraseñas ni claves privadas en este repositorio.
- Si GitHub no está disponible, Monitor Serial PALA debe continuar funcionando normalmente sin el contenido promocional.
- Cambiar este archivo no modifica ni interrumpe la comunicación USB o Bluetooth del monitor.
