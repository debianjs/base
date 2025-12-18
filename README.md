## como se arranca esto xd

Primero que nada, necesitas instalar las dependencias. Abre tu terminal en la carpeta del proyecto y corre:

```bash
npm install
```

Una vez que termine, simplemente inicia el bot con:

```bash
npm start
```

Verás un código QR en la terminal. ¡Escanéalo con tu WhatsApp (Dispositivos vinculados) y listo! El bot estará conectado.

## Estructura del proyecto :P

Para que no te pierdas, aquí está lo importante:

- **`index.js`**: Es el corazón del bot, aquí arranca todo.
- **`plugins/`**: Aquí ocurre la magia bro Cada archivo `.js` que pongas aquí será un comando nuevo.
- **`lib/`**: Cosas técnicas que hacen que el bot funcione (conexión, manejo de mensajes, cargador de plugins). Mejor no tocar mucho aquí a menos que sepas lo que haces. 😉

## Creando nuevos comandos (Plugins)

Es súper fácil, nomas crea un archivo nuevo en la carpeta `plugins/` (por ejemplo, `saludo.js`) y usa esta estructura:

```javascript
export default {
    // El comando que usará la gente (ej: /hola)
    command: ['hola', 'hello'], 
    
    // La función que se ejecuta
    execute: async ({ sock, m, args }) => {
        // Enviar un mensaje respondiendo al usuario
        await sock.sendMessage(m.key.remoteJid, { text: '¡Hola! ¿Cómo estás?' }, { quoted: m });
    }
};
```

¡Y ya está! No necesitas reiniciar el bot ni registrar nada más. El sistema lo detectará automáticamente (o al reiniciar si cambiaste algo estructural).

## 📝 Notas
- El prefijo por defecto es `/`.
- Si necesitas ver los logs de conexión, revisa la consola.
- La sesión de WhatsApp se guarda en la carpeta `auth_info_baileys`, así que no tendrás que escanear el QR cada vez.

si no entiendes algo me avisas xd