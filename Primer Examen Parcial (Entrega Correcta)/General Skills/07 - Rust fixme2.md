#### Descripción 
The Rust saga continues? I ask you, can I borrow that, pleeeeeaaaasseeeee?
Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/babfbee79718a6363826ba86300173ffde6d81577e9dd07d4130c53a7eecf6c3/fixme2.tar.gz).
#### Solución
```
rosyperez@MacBookAir Rust % mkdir fixme2; cd fixme2
rosyperez@MacBookAir fixme2 % ls
rosyperez@MacBookAir fixme2 % curl -O https://challenge-files.picoctf.net/c_verbal_sleep/babfbee79718a6363826ba86300173ffde6d81577e9dd07d4130c53a7eecf6c3/fixme2.tar.gz
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  1585  100  1585    0     0   4828      0 --:--:-- --:--:-- --:--:--  4832
rosyperez@MacBookAir fixme2 % ls
fixme2.tar.gz
rosyperez@MacBookAir fixme2 % tar -xzvf fixme2.tar.gz
x fixme2/
x fixme2/Cargo.toml
x fixme2/Cargo.lock
x fixme2/src/
x fixme2/src/main.rs
rosyperez@MacBookAir fixme2 % ls
fixme2 fixme2.tar.gz
rosyperez@MacBookAir fixme2 % cd fixme2
rosyperez@MacBookAir fixme2 % ls
Cargo.lock Cargo.toml src
rosyperez@MacBookAir fixme2 % cd src
rosyperez@MacBookAir src % ls
main.rs
rosyperez@MacBookAir src % nano main.rs
rosyperez@MacBookAir src % cargo run                                                                                                                         
   **Compiling** crossbeam-utils v0.8.20
   **Compiling** rayon-core v1.12.1
   **Compiling** either v1.13.0
   **Compiling** crossbeam-epoch v0.9.18
   **Compiling** crossbeam-deque v0.8.5
   **Compiling** rayon v1.10.0
   **Compiling** xor_cryptor v1.2.3
   **Compiling** rust_proj v0.1.0 (/Users/rosyperez/Seba/Trabajos/Seguridad/picoCTF/GeneralSkills/Rust/fixme2/fixme2)
    **Finished** `dev` profile [unoptimized + debuginfo] target(s) in 3.07s
    **Running** `/Users/rosyperez/Seba/Trabajos/Seguridad/picoCTF/GeneralSkills/Rust/fixme2/fixme2/target/debug/rust_proj`
Using memory unsafe languages is a: PARTY FOUL! Here is your flag: picoCTF{4r3_y0u_h4v1n5_fun_y31?}
rosyperez@MacBookAir src %
```
#### Notas
Tuve que aprender cn respecto a un lenguaje que no conocia y un manejo de espacio en memoria que tampoco tuve que consultar y comprar con otros lenguajes para entender que era borrow en rust, los fixes fueron fáciles
#### Referencias