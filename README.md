# Enarx-Bulletproof-Demo

This Demo shows how to implement Bulletproofs, a short non-interactive zero knowledge proof, in rust on top of Enarx. The scnenario underlying this demo is that we are carrying out a confidential transaction on a trusted execution environment using zero knowledge proof of knowledge, in order to carry out secure verification.

Zero Knowledge proof is a certain proof that proves that a certain statement is true without revealing the secret that the statement is about. This is normally done by making commitments to the secret that the statement is all about and sharing the commitment along with the proof. In this system, two actors are involved:- Prover :  the prover will create a proof to prove that he know the secret, Verifier : the verifier will verify the claim or the proof by the prover.


In this demo, we are implementing a bulletproof range proof that proves the secret value we have is in certain range along with a commitment to the secret so that we can successfully verify the secret. For creating the commitment, I am using Pedersen Commitment which uses a blinding factor and ellliptical function to mask data and still make it possible to verify the secret by using additive properties of the function. And using rangeproof we can verify that the value is within a range and in turn validate the transaction.

## Setup

In order to run this demo, you need to have the following 

### Rust

You can install Rust by using the following command:

```bash
$ curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y
$ source $HOME/.cargo/env

```

### Enarx

You can install Enarx by using [Enarx Documentation](https://enarx.dev/docs/Installation/Enarx)


## Code

```bash
git clone https://github.com/shravi24/Enarx-Bulletproof-Demo
cd Enarx-Bulletproof-Demo/code
cargo build --target=wasm32-wasi
enarx run target/wasm32-wasi/debug/bp-test1.wasm

```
## Video Demo
[Bulletproof](https://youtu.be/9GEZ1pnGN0I?t=943)
