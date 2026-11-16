# MOON · Simulador de paciente

Copia de la [página de pacientes](https://proyectomoon.github.io/Paciente/) en **modo simulador**, para probar las alertas sin tener puesta la pulsera.

**Web:** https://proyectomoon.github.io/TestPacientes/

## Cómo se usa
1. Entrá con la **contraseña de administrador**. No hace falta crear una cuenta.
2. En el **Panel de pruebas** de arriba:
   - **Pulso** y **Oxígeno en sangre**: mové el control deslizante o escribí el valor. Al lado se ve si cae en Normal, Irregular o Crítico.
   - **Acelerómetro**: con **Simular caída** se manda un pico de impacto, o podés elegir los g a mano y tocar **Enviar aceleración**.
   - **Escenarios**: Normal, Irregular, Hipoxia, Taquicardia y Bradicardia.
   - **Transmisión en vivo**: manda una lectura por segundo, igual que la pulsera.
   - **Mandar mails reales**: está apagado por defecto y los mails se simulan. Para recibirlos de verdad, cargá un email en "Editar perfil".
   - **Registro de alertas**: lista cada alarma y cada mail.

Los valores pasan por **la misma lógica** de la página real: los mismos umbrales, el mismo diagnóstico y la misma alarma cada 10 s.

## Cambiar la contraseña
La contraseña no está escrita en el código. Solo se guarda su hash SHA-256 en `TP_ADMIN_HASH`, dentro de `index.html`. Para cambiarla, abrí la página, ejecutá en la consola del navegador:

```js
tpHash('mi-clave-nueva').then(console.log)
```

y pegá el resultado en `TP_ADMIN_HASH`.
