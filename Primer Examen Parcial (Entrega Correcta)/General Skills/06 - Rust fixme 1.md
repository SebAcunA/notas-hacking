#### Descripción 
Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag!

Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/3f0e13f541928f420d9c8c96b06d4dbf7b2fa18b15adbd457108e8c80a1f5883/fixme1.tar.gz).
#### Solución
```
**info:** downloading installer
**warn:** It looks like you have an existing rustup settings file at:
**warn:** /Users/rosyperez/.rustup/settings.toml
**warn:** Rustup will install the default toolchain as specified in the settings file,
**warn:** instead of the one inferred from the default host triple.
**Welcome to Rust!**
This will download and install the official compiler for the Rust
programming language, and its package manager, Cargo.
Rustup metadata and toolchains will be installed into the Rustup
home directory, located at:
  /Users/rosyperez/.rustup  
This can be modified with the RUSTUP_HOME environment variable.  
The Cargo home directory is located at:  
  /Users/rosyperez/.cargo
This can be modified with the CARGO_HOME environment variable.  
The **cargo**, **rustc**, **rustup** and other commands will be added to
Cargo's bin directory, located at:
  /Users/rosyperez/.cargo/bin
This path will then be added to your **PATH** environment variable by
modifying the profile files located at:  
  /Users/rosyperez/.profile
  /Users/rosyperez/.zshenv
  /Users/rosyperez/.tcshrc
You can uninstall at any time with **rustup self uninstall** and
these changes will be reverted.
Current installation options:
   default host triple: **aarch64-apple-darwin**
     default toolchain: **stable (default)**
               profile: **default**
  modify PATH variable: **yes**
1) Proceed with standard installation (default - just press enter)
2) Customize installation
3) Cancel installation
>1
**info:** profile set to default
**info:** default host triple is aarch64-apple-darwin
**info:** syncing channel updates for stable-aarch64-apple-darwin
**info:** latest update on 2026-04-16 for version 1.95.0 (59807616e 2026-04-14)
**info:** downloading 6 components
        **cargo** installed                        8.33 MiB
       **clippy** installed                        2.81 MiB
    **rust-docs** installed                       21.27 MiB
     **rust-std** installed                       26.05 MiB
        **rustc** installed                       64.52 MiB
      **rustfmt** installed                        1.44 MiB                                                                                                                            **info:** default toolchain set to stable-aarch64-apple-darwin
  **stable-aarch64-apple-darwin installed** - rustc 1.95.0 (59807616e 2026-04-14)    
**Rust is installed now. Great!**
To get started you may need to restart your current shell.
This would reload your **PATH** environment variable to include
Cargo's bin directory ($HOME/.cargo/bin).  
To configure your current shell, you need to source
the corresponding **env** file under $HOME/.cargo.  
This is usually done by running one of the following (note the leading DOT):
. "$HOME/.cargo/env"            # For sh/bash/zsh/ash/dash/pdksh
source "$HOME/.cargo/env.fish"  # For fish
source "~/.cargo/env.nu"  # For nushell
source "$HOME/.cargo/env.tcsh"  # For tcsh
. "$HOME/.cargo/env.ps1"        # For pwsh
source "$HOME/.cargo/env.xsh"   # For xonsh
rosyperez@MacBookAir src % ls
main.rs
rosyperez@MacBookAir src % cargo run
zsh: command not found: cargo
rosyperez@MacBookAir src % source $HOME/.cargo/env
rosyperez@MacBookAir src % cargo run
    **Updating** crates.io index
  **Downloaded** crossbeam-deque v0.8.5
  **Downloaded** xor_cryptor v1.2.3
  **Downloaded** either v1.13.0
  **Downloaded** crossbeam-utils v0.8.20
  **Downloaded** crossbeam-epoch v0.9.18
  **Downloaded** rayon-core v1.12.1
  **Downloaded** rayon v1.10.0
  **Downloaded** 7 crates (379.2KiB) in 0.52s
   **Compiling** crossbeam-utils v0.8.20
   **Compiling** rayon-core v1.12.1
   **Compiling** either v1.13.0
   **Compiling** crossbeam-epoch v0.9.18
   **Compiling** crossbeam-deque v0.8.5
   **Compiling** rayon v1.10.0
   **Compiling** xor_cryptor v1.2.3
   **Compiling** rust_proj v0.1.0 (/Users/rosyperez/Seba/Trabajos/Seguridad/picoCTF/GeneralSkills/Rust/fixme1)
    **Finished** `dev` profile [unoptimized + debuginfo] target(s) in 7.57s
     **Running** `/Users/rosyperez/Seba/Trabajos/Seguridad/picoCTF/GeneralSkills/Rust/fixme1/target/debug/rust_proj`
"picoCTF{4r3_y0u_4_ru$t4c30n_n0w?}"≈
```
#### Notas
Había que corregir los errores señalados con comentarios y finalmente correr el código, no tenía instalado rust entonces lo instalé
#### Referencias