# Inventory Managoat
A Simple Command Line Inventory Manager.  
Prevent food waste and never lose track of your items!

## Description
Use Inventory Manager to keep a list of things that you own.  
It provides simple but effective ways to interact with this list.  

To see all available options:
```sh
inv --help
inv <SUBCOMMAND> --help
```

## Common Usage

Create and print new item types:
```sh
# Creates the "Toilet Paper" type. You always want to keep at least 5 of those.
inv ct "Toilet Paper" --minimum-quantity 5
>1 # The ID for toilet paper
# Creates the "Milk" type which stays fresh one week.
inv ct "Milk" --ttl "1week"
>2 # The ID for milk
# Show the existing types.
inv rt
```

Create a new item instance (a specific item that exists):
```sh
# Creates 3 instances of toilet paper (ID = 0)
inv ci 1 --quantity 3
>2 # Instance ID for those three toilet paper rolls
# List instances
inv ri
```

List items that you don't have enough of:
```sh
inv list-missing
```

List items that expired (I wouldn't suggest eating those!):
```sh
inv list-expired
```

Use an item:
```sh
# Use a toilet paper instance (ID = 2)
inv use 2
```

Put an item to the trash:
```sh
# Trash a toilet paper instance (ID = 2)
inv trash 2
```

## Install Using Cargo
First, install Rust (using [rustup](https://rustup.rs/)).
Then, it is as simple as:
```sh
cargo install -f inv
```

## Build From Source
First, install Rust (using [rustup](https://rustup.rs/)).

Then, run the following to build from source:
```sh
# Create a local copy
git clone https://github.com/Hauptling12/inventory-managoat
cd inventory-managoat

# Build from source files
cargo build --release

# (Optional) Install for the current user
mv target/release/inv ~/.local/bin/inv
```

