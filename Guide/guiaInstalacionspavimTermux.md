# Documentación para instalar spaVim en Termux 
>Tome este manual como un complemento para que su editor funcione correctamente, ya que puede omitirlo pero a largo o corto plazo le va a pedir dependencias o requisitos adicionales que ni usted mismo logrará encontrar, o puede que si, pero mejor instalarlos ahora mismo.

1) **Escoger repositorio por defecto**

    -
        ```sh
        termux-change-repo
        ```
    
        Seleccionar ***Default repositories***, y actualizar dicho repositorio:

    -
        ```sh
        pkg upgrade
        ```

2)  **Copie y pegue lo siguiente en la terminal:**

    -
        ```sh
        sh -c 'curl -fLo "${XDG_DATA_HOME:-$HOME/.local/share}"/nvim/site/autoload/plug.vim --create-dirs \
       https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim'
        ```

3) **Conceder permisos de almacenamiento a Termux**

    -
        ```sh
        termux-setup-storage
        ```

4) **Instalar neovim**

    -
        ```sh
        pkg install neovim
        ```
5) **Instalar python3**

    -
        ```sh
        pkg install python3
        ```
6) **Instalar pacman**

    -
        ```sh
        pkg install pacman
        ```

>En lo posible queremos evitar esas líneas rojas feas que aparecen cuando hay errores, muchas veces me he encontrado con lo siguiente: **No "python3" provider found. Run :checkhealth provider**

Asi que en la terminal ingresaremos lo siguiente:

-   
    ```sh
    python3 -m pip install --user --upgrade pynvim
    ```
7) **Instalar curl**

    -
        ```sh
        pkg install curl
        ```
8) **Instalar wget**

    -
        ```sh
        pkg install wget
        ```
9) **Instalar nodejs**
    
    -
        ```sh
        pkg install nodejs-lts
        ```
10) **Instalar ripgrep**

    De seguro conoce TELESCOPE (un buscador difuso altamente extensible sobre listas. Según la descripción en su repositorio)
    
    ![ImageDeTelescope](https://camo.githubusercontent.com/3d59e34d1f406890adf620546d3d97017ce0aacda034b1788c66fa872f192134/68747470733a2f2f692e696d6775722e636f6d2f5454546a6136742e676966)
    Pues este Plugin necesita unas pocas dependencias:
    
- [Ripgrep](https://github.com/BurntSushi/ripgrep):
    
    ```sh
    pkg install ripgrep
    ```
    
- [fd](https://github.com/sharkdp/fd#installation):
        
    ```sh
    pkg install fd
    ```
    
- [Tree-sitter](https://pypi.org/project/tree-sitter/):

    ```sh
    pip3 install tree_sitter
    ```

11)  **Instalar yarn**
        ```sh
        pkg install yarn
        ```

12) **Instalar [Lazygit](https://github.com/jesseduffield/lazygit)**
( Administrador de git )
    
    ```sh
    pkg install lazygit
    ```
    
13) **Instalar [Glow](https://github.com/charmbracelet/glow)** (Markdown)
    
    ![gifRelacionadoConGlow](https://camo.githubusercontent.com/bd591b74af8a6991894c8a84ab8d48f05ce7f66975b325d31f6954c836ddab27/68747470733a2f2f73747566662e636861726d2e73682f676c6f772f676c6f772d312e332d747261696c65722d6769746875622e676966)
        
    spaVim ya **cuenta con un live server para Markdown** pero tambien puede usar la terminal de manera local para visualizar estos archivos 

-
    ```sh
    pkg install glow
    ```


> Ingrese el comando glow dentro de la carpeta en donde se encuentran sus archivos .md para visualizarlos 

### Crear carpeta .config

-
    ```sh
    mkdir ~/.config
    ```

### Crear carpeta nvim

-
    ```sh
    mkdir ~/.config/nvim
    ```
-
    ```sh
    cd ~/.config/nvim
    ```

### Crear archivo init.vim e ingresar mediante neovim a el

-
    ```sh
    nvim init.vim
    ```
### Copiar y pegar los plugins

-
    Diríjase al siguiente **[link](https://raw.githubusercontent.com/spavim/spaVim-Termux/main/init.vim)** y copie todo el contenido, luego péguelo en el archivo init desde Termux

-
    Guarde y cierre el archivo mediante <code>:wq</code>

-
    Vuelva a ingresar al archivo para instalar los plugins

### En modo comandos, instale los plugins

-
    <code>:PlugInstall</code>

-
    Salga del editor:
    <code>:wq</code>

>🎉 Ahora ingrese de nuevo al editor y disfrute de ***[spaVim](https://github.com/spavim/spaVim)*** 🎉

En caso de errores post-instalación vaya a **[errores](https://github.com/spavim/spaVim/blob/main/Errors/Errors.md)**, en donde posiblemente encontrará el suyo, en caso contrario **[formúlelo aquí](https://github.com/spavim/spaVim-Termux/discussions/categories/errors)** para que los demás o el propio owner del repositorio puedan ayudarlo
