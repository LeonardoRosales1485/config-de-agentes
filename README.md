# Configuración global de opencode

Agentes y configuración compartida para opencode, pensada para usarse en distintas PC.

## Agentes incluidos

Un agente primario (`primary`) orquesta el trabajo y 10 subagentes especializados (`subagent`) ejecutan tareas específicas. Los subagentes solo responden cuando el orquestador los invoca.

| Agente | Modo | Rol |
|---|---|---|
| `my-orchestrator` | `primary` | Estratega principal. Nunca codea, solo delega tareas a los subagentes y pide clarificación al usuario. |
| `my-planner` | `subagent` | Transforma requerimientos en un plan accionable y lo valida con el usuario. |
| `my-researcher` | `subagent` | Investiga preguntas complejas y documentación de APIs. No escribe código. |
| `my-story-maker` | `subagent` | Convierte requerimientos en user stories con criterios de aceptación. |
| `techlead` | `subagent` | Evalúa requerimientos y define stack tecnológico, arquitectura e infraestructura. |
| `backend` | `subagent` | Implementa APIs, lógica de servidor y esquemas de base de datos. |
| `frontend` | `subagent` | Construye componentes UI, páginas y estilos según el diseño del proyecto. |
| `tests` | `subagent` | Escribe y ejecuta tests unitarios, de integración y e2e. |
| `validator` | `subagent` | Ejecuta linters, type checkers y formateadores para validar calidad. No corrige. |
| `security` | `subagent` | Revisa vulnerabilidades (OWASP, inyecciones, auth). No hace correcciones. |
| `devops` | `subagent` | Configura CI/CD, Docker, infraestructura cloud y estrategias de deploy. |

### Flujo de trabajo típico

1. El usuario describe una tarea → `my-orchestrator` la recibe
2. `my-orchestrator` delega a los subagentes según corresponda
3. Cada subagente ejecuta su especialidad y reporta resultados
4. `my-orchestrator` consolida y presenta el resultado al usuario

## Instalación en una PC nueva

```powershell
# 1. Clonar el repo en la ruta de configuración global
git clone https://github.com/LeonardoRosales1485/config-de-agentes.git "$env:USERPROFILE\.config\opencode"

# 2. Si usás plugins con dependencias npm, instalar
cd "$env:USERPROFILE\.config\opencode"
npm install
```

## Actualizar desde otra PC

```powershell
cd "$env:USERPROFILE\.config\opencode"
git pull
```

## Hacer cambios y subirlos

```powershell
cd "$env:USERPROFILE\.config\opencode"
git add -A
git commit -m "descripción del cambio"
git push
```
