# arbitrum-api-pump.fun

# Effortlessly Buy Tokens on Pump.fun Using Arbitrum APIs

Looking to quickly buy tokens using the latest bonding curves on Pump.fun? The Pump.fun Buy API on Arbitrum is designed for fast and efficient token purchases, optimized for seamless trading on the Arbitrum network.

## Why Use the Pump.fun Buy API?

The Pump.fun Buy API allows you to effortlessly purchase tokens through a simple POST request. Optimized for speed and reliability, it ensures fast transaction processing, making it ideal for anyone looking to buy tokens on Pump.fun with minimal hassle.

## Key Features

- **Fast and Efficient Trading**: Enjoy smooth and rapid transactions using our optimized API on the Arbitrum network.
- **Easy Integration**: The API integrates easily with any programming language, ensuring a seamless setup process.
- **Customizable Parameters**: Customize transaction parameters like slippage and fee settings to optimize your token purchase experience.

## How to Buy Tokens on Pump.fun Using Arbitrum APIs

To buy tokens on Pump.fun via the Pump.fun Buy API, send a POST request with the following parameters:

- **private_key**: The private key of the wallet used to pay for the transaction and associated fees.
- **mint**: The mint address of the ERC-20 token you wish to purchase (e.g., USDT, DAI, or another supported token on Arbitrum).
- **amount**: The amount of the selected ERC-20 token you want to purchase (e.g., 100 USDT).
- **slippage**: Your desired slippage percentage (e.g., 10 for 10%, or 1 for 1%).

## API Endpoint

Use the following endpoint to buy tokens:

**Buy API Endpoint**:  
`https://arbitrum-api.co/api/pumpfun/buy`

## Optimizing Your Transactions

For optimal results, the default parameters for fee and transaction settings are:

- **microlamports**: `1000000` (Transaction fee of approximately 0.001 in the native Arbitrum asset).
- **units**: `1000000` (Controls transaction speed and execution).

If needed, consider adjusting the slippage and fee parameters to speed up the transaction or improve execution reliability.

## Example of a Request to Buy Tokens

To make a purchase request, you can use the following Python code with the `requests` library:

```python
import requests

# Replace these values with your actual test values
private_key = ''  # Your private key
mint = ''         # ERC-20 token mint address (e.g., USDT, DAI)
amount = 100      # Amount of the token to purchase
slippage = 10     # 10% slippage

def test_buy_request():
    url = 'https://arbitrum-api.co/api/pumpfun/buy'
    payload = {
        "private_key": private_key,
        "mint": mint,
        "amount": amount,
        "slippage": slippage,
    }

    try:
        response = requests.post(url, json=payload)
        response.raise_for_status()  # Raise an exception for HTTP errors
        print('Response:', response.json())
    except requests.exceptions.RequestException as e:
        if response := e.response:
            print('Error:', response.json())
        else:
            print('Error:', e)

# Run the function
test_buy_request()

Example Successful Response

{
  "status": "success",
  "txid": "0xabcdef1234567890abcdef1234567890abcdef1234567890abcdef1234567890"
}

Example Failed Response

{
  "status": "failed",
  "message": "Transaction failed due to insufficient gas.",
  "error": "Insufficient funds in wallet for gas fees."
}

Contact Information

These APIs are in the testing phase, and your feedback is valuable. Please feel free to report any issues or suggest improvements.

    Support: support@arbitrum-api.co
    Bug Reports: bugs@arbitrum-api.co
