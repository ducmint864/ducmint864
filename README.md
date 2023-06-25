#### Hello Wolrd
I'm a 1st year undergrad student from University of Information technology, Ho Chi Minh city, Vietnam
![](https://github.com/ducmint864/Gifs/blob/main/xUPGcmqgta8tf7Xak8.gif)

 #### Blockchain 🟪⛓️🟦⛓️🟦⛓️🟦⛓️🟦
I'm faithful that 'Blockchain' tech will be significant in the near future, based on the fact that as it has so much potential to transform the underlying insfrastructure of the Internet, along with the capabilities to collab with or integrated into other techs like AI ... Nevertheless, 'Blockchain' tech is still somewhat immature, just like the Internet in the early 90s. Good sign is that more builders are starting to realize its hidden power and helping it develop rapidly. Blockchain opens up a vision into the future filled with possibilities, why not take this opportunity to build the future together and become a part of history. For more details, read 'blockchain revolution' by Don Tapscott.
```C++
#include <vector>
#include <memory>
#ifndef Blockchain_H
    #define Blockchain_H
#endif



class Node;



class Block
{

    private:
        std::string m_correctHash;
        std::string m_prevHash; // hash of previous block in blockchain

    public:
        std::string m_transactionsData;
        uint32_t m_timestamp;

        // constructor
        Block(std::string& ar_transactionData, std::string& ar_prevHash);

        // empty constructor
        Block();
        
        // destructor
        ~Block();
        
    friend class Blockchain;

};


class Blockchain
{

    public:
        std::vector<std::unique_ptr<Block>> m_chain;
        std::string m_tmpTransactionsData;
        uint64_t m_currentIndex = -1; // current index is also always the last index in chain (if nothing went wrong)

        // constructor
        Blockchain ();

        // destructor
        ~Blockchain();
}
```
#### What do you want the future to look like?

### About me
- 🔭 I’m enthusiastic in: Linux, Cloud, big data, web development(including Web3), defi, smart contract development
- 🌱 I’m currently learning blockchain and smart contract development
- 👯 I’m looking for passionate people to learn from and collab with
- 🤔 I’m looking for help with ...
- ⚡ Knowledge: C/C++, Javascript, Solidity, Python, Linux
🌀Godspeed :D
![](https://github.com/ducmint864/Gifs/blob/main/cSdSijzwrsliuI1hnC.gif)
