# Sueños y Cábala

App para interpretar sueños inspirada en la Cábala. La persona cuenta su sueño, elige cómo se sintió y recibe una interpretación personal escrita por Claude (la IA de Anthropic). Después puede pedir una consulta personalizada.

## Qué hay en esta carpeta

| Archivo | Para qué sirve |
|---|---|
| `index.html` | La app (lo que ve la gente). |
| `api/interpretar.js` | El servidor que pide la interpretación a Claude. Guarda tu clave en secreto. |
| `package.json` | Lista lo que necesita el servidor para funcionar. |
| `perfil.html` | Tu página personal antigua (Instagram y Vinted). |

## Cómo publicarla (una sola vez, unos 15 minutos)

### 1. Consigue tu clave de Claude
1. Entra en **console.anthropic.com** y crea una cuenta.
2. Añade un método de pago y carga saldo (con 5–10 € tienes para empezar).
3. **Pon un límite de gasto mensual** en *Settings → Limits* (por ejemplo, 20 €). Así nunca gastarás más de eso, pase lo que pase.
4. Ve a *API Keys*, crea una clave y cópiala. Empieza por `sk-ant-`.
   **No la compartas con nadie ni la pegues en ningún chat.**

### 2. Publica la web en Vercel (gratis)
1. Entra en **vercel.com** y regístrate con tu cuenta de GitHub.
2. Pulsa **Add New → Project** y elige el repositorio `cora.-`.
3. Antes de darle a *Deploy*, abre **Environment Variables** y añade:
   - Nombre: `ANTHROPIC_API_KEY`
   - Valor: la clave que copiaste en el paso 1
4. Pulsa **Deploy**. En un minuto tendrás una dirección del tipo `suenos-y-cabala.vercel.app`.

### 3. Prueba que funciona
Abre tu dirección, escribe un sueño y pulsa *Interpretar*. Si ves aparecer el texto poco a poco, ya está todo listo.

## Lo que cuesta

Cada interpretación cuesta **unos 2–4 céntimos**. 100 sueños al mes son unos 3 €. El límite del paso 1 te protege de cualquier sorpresa.

## Tus datos de contacto

Al principio del script de `index.html` está el bloque `CONSULTA`. Ahí se ponen tu WhatsApp, tu Instagram, el precio y el plazo de respuesta de la consulta personalizada.

## Seguridad

- La clave solo está en Vercel. La página nunca la ve, así que nadie puede copiarla.
- El servidor solo acepta peticiones de tu propia web y sueños de hasta 3000 caracteres.
- El sueño se envía a Anthropic para escribir la interpretación. Ni la web ni el servidor lo guardan. El diario de sueños se queda en el móvil de cada persona.
