# 🏦 **CryptoBank - Multiuser Ethereum Vault**

## 📝 **Overview**

**CryptoBank** es un contrato inteligente que actúa como un banco descentralizado en Ethereum. Permite a múltiples usuarios depositar y retirar sus propios ethers, con un límite máximo configurable por el administrador.

> [!NOTE]\
> Este contrato no emite tokens, opera exclusivamente con **ETH** y garantiza la seguridad mediante restricciones de usuario y un límite máximo de balance.

### 🔹 **Key Features:**

- ✅ **Depósitos y retiros seguros** solo por parte del propietario de los fondos.
- ✅ **Balance máximo configurable** para evitar acumulación excesiva por usuario.
- ✅ **Arquitectura multiusuario** sin interferencia entre cuentas.
- ✅ **Administrador con permisos especiales** para modificar parámetros críticos.

---

## ✨ **Features**

### 💰 Depósitos de Ether

- Cualquier usuario puede depositar Ether en su cuenta individual.
- El depósito se limita por usuario a un balance máximo predefinido.

### 💸 Retiros de Ether

- Cada usuario puede retirar únicamente el Ether que ha depositado.
- Los fondos se transfieren directamente a la dirección del usuario.

### ⚙️ Administración Segura

- Solo el administrador puede cambiar el balance máximo por usuario.
- Acciones sensibles protegidas por `modifier onlyAdmin`.

---

## 📖 **Contract Summary**

### 🔧 **Core Functions**

| Function Name                    | Description                                                    |
| -------------------------------- | -------------------------------------------------------------- |
| `depositEther()`                 | Permite a un usuario depositar Ether (si no supera el límite). |
| `withdrawEther(uint256 amount_)` | Permite retirar el Ether depositado por el usuario.            |
| `modifyMaxBalance(uint256)`      | Solo el admin puede cambiar el límite máximo de depósito.      |

---

## ⚙️ **Prerequisites**

### 🛠️ Tools Required:

- **Remix IDE**: Para desplegar y probar el contrato ([Remix](https://remix.ethereum.org))
- **MetaMask Wallet**: Para interactuar con la red Ethereum.

### 🌐 Environment:

- **Solidity Compiler Version**: `0.8.28`
- **Redes compatibles**: Local (JavaScript VM) o testnets como Goerli/Sepolia.

> [!TIP]\
> Es recomendable probar en testnets antes de desplegar en mainnet.

---

## 🚀 **How to Use the Contract**

### 1️⃣ **Desplegar el contrato**

1. Abre [Remix](https://remix.ethereum.org)
2. Crea un nuevo archivo `CryptoBank.sol` y pega el código.
3. En la pestaña de **Solidity Compiler**:
   - Selecciona la versión `0.8.28`.
   - Haz clic en **Compile**.
4. En la pestaña **Deploy & Run Transactions**:
   - Elige el entorno `Injected Web3` si usas MetaMask.
   - Ingresa los parámetros:
     - `maxBalance`: por ejemplo, `5000000000000000000` (5 ether en wei).
     - `admin`: tu dirección de Ethereum.
   - Haz clic en **Deploy** 🚀

### 2️⃣ **Uso básico**

#### 💰 A. Depositar Ether

1. Envía Ether al contrato usando la función `depositEther()`.
2. Asegúrate de no exceder el balance máximo permitido.

#### 💸 B. Retirar tus fondos

1. Llama a `withdrawEther(uint256 amount_)`.
2. El monto será transferido a tu dirección si tienes balance suficiente.

#### ⚙️ C. Modificar balance máximo (solo admin)

1. Llama a `modifyMaxBalance(uint256 newMax)` desde la cuenta admin.

> [!WARNING]\
> Nunca envíes Ether directamente al contrato sin llamar a `depositEther()`, ya que no se registrará en tu balance.

---

## 🧱 **Extending the Contract**

### 🔍 Posibles mejoras

- 🔒 **Límite por usuario individual** en lugar de un máximo global.
- 📟 **Historial de transacciones** con timestamps y tipos.
- 📊 **Panel frontend** para interacción visual.
- 🧑‍⚖️ **Mecanismo de penalización o verificación KYC**.

> [!CAUTION]\
> Si piensas utilizar este contrato en producción, asegúrate de auditar su seguridad con expertos.

---

## 📜 **License**

Este proyecto está licenciado bajo la **LGPL-3.0-only**.

---

### 🚀 **CryptoBank es un mini banco descentralizado para gestionar tus Ethers de forma segura y transparente.**

