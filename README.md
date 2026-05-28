# Configuración global de opencode

Agentes y configuración compartida para opencode, pensada para usarse en distintas PC.

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
