# Aula Extra --- Personalização do Ubuntu 26.04 (Estilo macOS)

## Objetivo

Transformar o Ubuntu 26.04 (GNOME 50.1) em um ambiente visual inspirado
no macOS.

## O que foi configurado

### Tema

-   WhiteSur GTK Theme
-   WhiteSur GNOME Shell
-   Tema Dark aplicado via GNOME Tweaks

### Ícones

-   WhiteSur Icon Theme

### Cursor

-   WhiteSur Cursor

### Login (GDM)

-   Tela de login personalizada
-   Wallpaper personalizado

### GRUB

-   Menu simplificado (Ubuntu + Windows)
-   Tema personalizado

### Dock

Extensões: - Dash to Dock - Blur My Shell - Burn My Windows - Just
Perfection

Configuração recomendada: - Posição: Inferior - Ícones: 56 px - Dock
flutuante - Ocultação automática - Ocultação inteligente - Ampliação dos
ícones (≈30%)

### Fontes

-   Extração das fontes SF Pro do pacote oficial da Apple (.dmg → .pkg →
    Payload)
-   Instalação em \~/.local/share/fonts
-   Atualização do cache com `fc-cache -fv`

### Papel de parede

-   Wallpaper personalizado no desktop
-   Wallpaper aplicado à tela de login

## Observações

-   O leitor de digitais Goodix (27c6:538d) não possui suporte funcional
    nativo no Ubuntu 26.04.
-   No GNOME 50.1 + Wayland, os botões coloridos (🔴🟡🟢) do WhiteSur
    podem não aparecer, mesmo com o tema corretamente aplicado. Os
    botões ficam no lado esquerdo, mas usam os ícones padrão do GNOME.

## Resultado

Sistema com aparência muito próxima ao macOS, mantendo estabilidade para
uso diário e desenvolvimento.
