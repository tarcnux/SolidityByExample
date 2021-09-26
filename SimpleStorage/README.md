# Exemplo SimpleStorage
        $ mkdir SimpleStorage
        $ cd SimpleStorage
        $ truffle init
        $ code .
        
## Criação do contrato limpo e compilação
        $ truffle create contract SimpleStorage
        contracts/SimpleStorage.sol
        $truffle compile

## Deploy e interação com o Ganache UI
Para se conectar ao Ganache UI deve habilitar o ambiente *development* em *network* na porta *7545*.

        /*truffle-config.js*/
        networks: {
            development: {
            host: "127.0.0.1",     // Localhost (default: none)
            port: 7545,            // Standard Ethereum port (default: none)
            network_id: "*",       // Any network (default: none)
            }
        }

No Ganache, na aba *Contracts* deve adicionar o caminho do *truffle-config.js*

        $ truffle migrate --network development
        $ truffle console --network development

        truffle(development)> let storage = await SimpleStorage.deployed()
        truffle(development)> storage.set(42)
        truffle(development)> (await storage.get()).toNumber()

Para sair deste ambiente basta digitar *Ctrl C* duas vezes


