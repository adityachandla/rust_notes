# Basics

### Project creation
To create a project use
```bash
cargo init project_name_snake_case
```
Snake case is the naming convention.

### Cargo basics
To run the project use
```bash
cargo run
```
To simply create a binary use
```bash
cargo build
```
The above command creates a binary in target/debug/[projectname]

### Basic Program
```rust
use std::io;  //Importing libraries

fn main() {
    println!("Enter a number"); //println! is a macro
    let mut number = String::new(); //forms a new string on heap

    io::stdin() //Gets the standard input
        .read_line(&mut number) //Reads the line into the mutable variable
        .expect("Unable to read from stdin"); //In case of error do this. We can also use ?

    println!("The number is {}", number); //Prints out the number. Curly braces capture parameters
}
```

### Generate a random number
First of all we need to add a dependency in the *Cargo.toml* file.
```
rand = "0.8.3"
```
After adding this, whenever we build this project, this dependency will get downloaded and installed.

To see documentation of all installed libraries, we can use this command:
```bash
cargo doc --open
```

Now to generate a random number, we can do something like this:
```rust
use rand::Rng;

fn main() {
	let num = rand::thread_rng().gen_range(1..101);
	println!("Random number is {}", num);
}
```

*Left at comparing the number part*
