# 0x Examples

A collection of 0x API code examples

## Swap API

- [Swap API Demo App (Next.js)](https://github.com/0xProject/0x-nextjs-demo-app/tree/main)
- [Swap API Demo App (HTML/CSS/JavaScript)](https://github.com/0xProject/swap-demo-tutorial)

## Tx Relay API

- [Tx Relay API Demo App (Next.js App Router)](https://github.com/0xProject/0x-examples/tree/main/tx-relay-next-app)

const main = async () => {

	 const sellAmount = parseUnits("1000", await usdc.read.decimals());

  	// fetch quote
  	const quoteParams = new URLSearchParams({
  		chainId: client.chain.id.toString(),
    	sellToken: usdc.address,
    	buyToken: weth.address,
    	sellAmount: sellAmount.toString(),
      taker: client.account.address,
    });

  const quoteResponse = await fetch(
    "http://api.0x.org/gasless/quote?" + quoteParams.toString(),
    {
      headers,
    }
  );

  const quote = await quoteResponse.json();
  console.log("Quote to swap 1000 USDC for WETH: ", quote);

}
main();
