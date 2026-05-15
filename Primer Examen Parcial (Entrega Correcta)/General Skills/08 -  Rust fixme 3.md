#### Descripción 
Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag!
Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/dcdaf491b35c1d0f5075e9583edbbb7aaea1dffb6ad32bc000e4d87b5200ff7b/fixme3.tar.gz).
#### Solución
 ```
 rosyperez@MacBookAir Rust % mkdir fixme3; cd fixme3
rosyperez@MacBookAir fixme3 % curl -O https://challenge-files.picoctf.net/c_verbal_sleep/dcdaf491b35c1d0f5075e9583edbbb7aaea1dffb6ad32bc000e4d87b5200ff7b/fixme3.tar.gz
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  1776  100  1776    0     0   5163      0 --:--:-- --:--:-- --:--:--  5177
rosyperez@MacBookAir fixme3 % tar -xzvf fixme3.tar.gz                                                                                                            
x fixme3/
x fixme3/Cargo.toml
x fixme3/Cargo.lock
x fixme3/src/
x fixme3/src/main.rs

rosyperez@MacBookAir fixme3 % cd src
cd: no such file or directory: src
rosyperez@MacBookAir fixme3 % ls
fixme3 fixme3.tar.gz
rosyperez@MacBookAir fixme3 % cd fixme
cd: no such file or directory: fixme
rosyperez@MacBookAir fixme3 % cd fixme3
rosyperez@MacBookAir fixme3 % cd src
rosyperez@MacBookAir src % nano main.rs
rosyperez@MacBookAir src % cargo run                                                                                                                           
   **Compiling** crossbeam-utils v0.8.20
   **Compiling** rayon-core v1.12.1
   **Compiling** either v1.13.0
   **Compiling** crossbeam-epoch v0.9.18
   **Compiling** crossbeam-deque v0.8.5
   **Compiling** rayon v1.10.0
   **Compiling** xor_cryptor v1.2.3
   **Compiling** rust_proj v0.1.0 (/Users/rosyperez/Seba/Trabajos/Seguridad/picoCTF/GeneralSkills/Rust/fixme3/fixme3)    **Finished** `dev` profile [unoptimized + debuginfo] target(s) in 3.00s
     **Running** `/Users/rosyperez/Seba/Trabajos/Seguridad/picoCTF/GeneralSkills/Rust/fixme3/fixme3/target/debug/rust_proj`
Using memory unsafe languages is a: PARTY FOUL! Here is your flag: picoCTF{n0w_y0uv3_f1x3d_1h3m_411}
rosyperez@MacBookAir src %
 ```
#### Notas
El reto consistía principalmente en corregir errores de sintaxis y ownership en Rust. Se modificó el parámetro `&String` a `&mut String` para permitir cambios sobre el texto usando `push_str()`. Además, el bloque `unsafe` no estaba correctamente cerrado porque el `}` había sido comentado accidentalmente, lo que provocaba errores de compilación. Este bloque era necesario debido al uso de punteros crudos (`raw pointers`) y la función `std::slice::from_raw_parts`, operaciones que Rust considera inseguras porque el compilador ya no puede garantizar automáticamente la seguridad de memoria.
#### Referencias
