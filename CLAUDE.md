# CLAUDE.md — MedInA Operating Principles

> **Para:** equipos LATAM que usan Claude Code, Cursor, Cowork u otros agentes de IA en producto B2B.
>
> **De:** Alejandro Medina (MedInA) + lecciones de 100+ frameworks propietarios validados en producción con clientes LATAM.
>
> **License:** MIT. Forkealo, adaptalo, mejóralo. Si te sirve, compartí.

## Por qué existe este archivo

La mayoría de las guías de "cómo trabajar con IA" son **genéricas, US-céntricas y técnicas**. Este archivo destila lo opuesto: **principios operativos para founders LATAM B2B** que ya están construyendo con agentes y necesitan que el agente sea **realmente útil**, no impresionante.

Inspirado en formato del [andrej-karpathy-skills](https://github.com/forrestchang/andrej-karpathy-skills) (4 principios, 109K stars). Acá hay 7. La diferencia: **estos están validados en deals reales LATAM, no derivados de un tweet**.

---

## Los 7 principios MedInA

### 1. Captura todo. Sintetiza después.

> **Mal:** "Espera, déjame pensarlo y te respondo bien."
>
> **Bien:** "Capturalo en `00-inbox/` ahora. La síntesis se hace en otro pase."

El cerebro humano + el agente IA tienen el mismo bug: **si no lo escribís, lo perdés**. La regla de oro: **capturar bruto siempre, curar después en lote**.

Implicación operativa:
- Carpeta `00-inbox/` en tu vault = primer destino de TODO lo nuevo
- Una rutina semanal (o un agente Routine F) clasifica y mueve
- Auto-clasificar al momento es alto riesgo (audio sin contexto, idea a medio formar)

### 2. La capacidad ya no es el diferenciador. El contexto sí.

> **Mal:** "Déjame migrar a GPT-5.2 que tiene 91% en MMLU."
>
> **Bien:** "Mi agente sabe cosas de mi cliente que el de mi competencia jamás sabrá."

Stanford AI Index 2026 confirmó: **top 4 modelos están a 25 puntos de Elo**. La diferencia comercial real ya no la hace el modelo. La hace **lo que tu agente sabe sobre tu vertical, tus clientes, tu compliance y tu manera de operar**.

Implicación operativa:
- Invertí 80% del tiempo en CONTEXTO (vault, frameworks, plantillas)
- Invertí 20% en MODELO (router para usar el adecuado por tarea)
- Si tu único diferenciador es "uso Claude Opus", no tenés diferenciador

### 3. El silencio del usuario NO es objeción. Es procesamiento.

> **Mal:** Bombardear al cliente con seguimiento cada 24h.
>
> **Bien:** Esperar. Si después de 4-5 días pensás que se enfrió, mandá UNA pregunta diseñada para "no": *"¿Has decidido seguir explorando otra opción?"*

Aplicable a ventas B2B y a agentes que esperan respuesta del usuario. Voss lo llamaba "the late night DJ effect" — calma y espacio. **El agente que persigue, pierde.**

Implicación operativa:
- Tu agente NO debe enviar más de 1 mensaje por día sin respuesta
- Cuando rompa el silencio, debe ser pregunta de "no", no de "sí"
- Trackear silencio del usuario como SEÑAL, no problema

### 4. Lo que no se mide, no escala.

> **Mal:** "Mi agente atiende mejor que un humano."
>
> **Bien:** "Mi agente cierra el 18% de leads en mensajes 5-9 vs 12% del baseline humano. n=240 conversaciones."

LATAM tiene una manía con la narrativa cualitativa ("se siente mejor"). Si querés escalar tu producto/servicio con IA: **medí algo accionable y repetible**.

Implicación operativa:
- Define UNA métrica norte por cliente/producto (North Star)
- Cohort analysis sobre esa métrica
- Si vas a inventar una métrica, asegurate que pueda BAJAR (no solo subir)

### 5. La IP no es el código. Es el contexto curado + el método.

> **Mal:** "Mi prompt es secreto industrial, no lo comparto."
>
> **Bien:** "Mi prompt es público. Lo que no podés copiar es: mis 240 conversaciones de cliente con feedback + el método de iteración + las 8 capas de fallback que aprendí cuando se rompió en Cartagena."

Cualquiera con Claude puede escribir un prompt. Lo que NADIE puede replicar de la noche a la mañana: **tu data, tu vertical, tus errores documentados, tu método de iteración**. Eso es el moat.

Implicación operativa:
- Compartí prompts. Los prompts son commodities.
- Protegé data + método + lecciones operacionales
- Documentá cada error en producción como activo (no como vergüenza)

### 6. Anti-overengineering: si no se rompió, no lo arregles.

> **Mal:** "Migramos a microservicios + Kubernetes + Pulsar para escalar a 10M usuarios."
>
> **Bien:** "Tenés 47 usuarios. Quedate en monolito hasta los 10K. Si llegás, paga ese problema."

LATAM tiene founders que copian arquitecturas de Silicon Valley para problemas de Argentina. Más infraestructura ≠ más profesional. **El stack mínimo viable que funciona es siempre superior al ideal teórico**.

Implicación operativa:
- Stack inicial: Drive + Supabase free + 1 VPS + Claude API. Eso aguanta hasta $50K MRR.
- No migres antes de tener problema real (latencia >2s, cost >$X/mo, downtime documentado)
- Cada migración premature te roba 2-4 semanas de revenue

### 7. El agente debe mejorar cada semana. Si no, no es agente — es script.

> **Mal:** "Implementé el agente en mi cliente y lo dejé corriendo."
>
> **Bien:** "Cada semana revisamos las 3 conversaciones que no cerraron y agregamos la corrección a la skill. El agente del cliente 50 recibirá esa corrección automáticamente."

La promesa del agente vs el script tradicional es **inteligencia compuesta**. Si tu agente no mejora cada semana, perdiste la única ventaja real que tenías sobre RPA + chatbots viejos.

Implicación operativa:
- Pipeline de captura de errores → catálogo de fixes → distribución automática
- Cliente que cancela el sistema = pierde la trayectoria de mejora (lock-in real)
- "Mantenimiento mensual" = MEJORA mensual, no solo "no se rompió"

---

## Cómo aplicar estos principios

### Para tu próximo proyecto

1. Antes de construir, **leé estos 7 principios** y marcá con qué luchás más
2. Empezá por el principio #1 (captura todo) — es el más barato y el de mayor ROI
3. Después #2 (contexto > modelo) — eso decide tu stack
4. Recién al mes siguiente, agregá los demás

### Para tu equipo

Pegá este archivo como `CLAUDE.md` en la raíz de tu proyecto. Claude Code y Cursor lo van a leer automáticamente y van a operar bajo estos principios.

```bash
# Bash / Linux / Mac
curl -L https://raw.githubusercontent.com/MedInA23-coder/medina-operating-principles/main/CLAUDE.md > CLAUDE.md
```

```powershell
# PowerShell / Windows
Invoke-WebRequest -Uri https://raw.githubusercontent.com/MedInA23-coder/medina-operating-principles/main/CLAUDE.md -OutFile CLAUDE.md
```

### Si querés más profundidad

Estos 7 principios son el "summary" de **88+ frameworks propietarios MedInA** validados en producción con clientes LATAM (consultoría IA, fintech, hotelería, dental, gobierno).

El catálogo completo se distribuye via **MedInA Skills Network** (suscripción profesional). Detalles: **medinaia.com/skills-network**.

---

## License

MIT — usalo, forkealo, mejóralo, vendelo si querés. Si te sirvió, mencionalo. Si lo mejorás, hacé PR (probablemente lo merge).

## Atribución

- Principios destilados por **Alejandro Medina** (MedInA, Colombia)
- Inspiración formato: [andrej-karpathy-skills](https://github.com/forrestchang/andrej-karpathy-skills)
- Validación empírica: 100+ deals B2B LATAM 2024-2026
- Datos citados: Stanford HAI AI Index Report 2026

## Contacto

Si esto te sirvió y querés explorar Skills Network o consultoría 1-on-1: **alejandro@medinaia.com**
