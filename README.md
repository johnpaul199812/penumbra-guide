# Penumbra Setup Guide for Ubuntu 20.04.6

Follow these steps to set up Penumbra on Ubuntu 20.04.6:

1. **Install Dependencies:**
    ```bash
    sudo apt-get install build-essential pkg-config libssl-dev clang git-lfs
    ```

2. **Clone Penumbra Repository:**
    ```bash
    git clone https://github.com/penumbra-zone/penumbra
    cd penumbra && git fetch && git checkout v0.71.0
    ```

3. **Build the Project:**
    ```bash
    cargo build --release
    ```

4. **Generate Wallet:**
    ```bash
    cargo run --quiet --release --bin pcli init soft-kms generate
    ```

5. **View Wallet Address:**
    ```bash
    cargo run --release --bin pcli view address 0
    ```

6. **Get Test Tokens:**
    - Copy your address and get test tokens in the Discord faucet.
    - Then check if received:
    ```bash
    cargo run --release --bin pcli view balance
    ```

7. **Open a New Tmux Session:**
    ```bash
    tmux new -t penumbra
    ```

8. **Contribute:**
    - Contribute to Penumbra:
    ```bash
    cargo run --release --bin pcli ceremony contribute --phase 2 --bid 90
    ```
    - Wait till it reaches your turn or bid more to increase your position.
