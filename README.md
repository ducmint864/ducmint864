https://github.com/ducmint864/ducmint864/assets/69887564/75231763-2d74-481a-84c5-e9bce1715a88
```yaml
  ___ ___   ___________ .____      .____      ________            __      __  ________    __________  .____      ________   
 /   |   \  \_   _____/ |    |     |    |     \_____  \          /  \    /  \ \_____  \   \______   \ |    |     \______ \  
/    ~    \  |    __)_  |    |     |    |      /   |   \         \   \/\/   /  /   |   \   |       _/ |    |      |    |  \ 
\    Y    /  |        \ |    |___  |    |___  /    |    \         \        /  /    |    \  |    |   \ |    |___   |    `   \
 \___|_  /  /_______  / |_______ \ |_______ \ \_______  /          \__/\  /   \_______  /  |____|_  / |_______ \ /_______  /
       \/           \/          \/         \/         \/                \/            \/          \/          \/         \/ 
(＾Ｕ＾)ノ~ I'm Minh, a 1st year student at University of Information Technology, Ho Chi Minh City, Vietnam
```
<p align="center">
  <img src="https://github.com/ducmint864/Gifs/blob/main/NKEt9elQ5cR68.gif" alt="Your GIF" width="100%">
</p>

<p align="center">
  <img src="https://github.com/ducmint864/Gifs/blob/main/pVGsAWjzvXcZW4ZBTE.gif" alt="Your GIF" width="100%">
</p>

``` python
 .----------------.  .----------------.  .----------------.  .----------------.  .----------------.  .----------------.  .----------------.  .----------------.  .----------------.  .-----------------.
| .--------------. || .--------------. || .--------------. || .--------------. || .--------------. || .--------------. || .--------------. || .--------------. || .--------------. || .--------------. |
| |   ______     | || |   _____      | || |     ____     | || |     ______   | || |  ___  ____   | || |     ______   | || |  ____  ____  | || |      __      | || |     _____    | || | ____  _____  | |
| |  |_   _ \    | || |  |_   _|     | || |   .'    `.   | || |   .' ___  |  | || | |_  ||_  _|  | || |   .' ___  |  | || | |_   ||   _| | || |     /  \     | || |    |_   _|   | || ||_   \|_   _| | |
| |    | |_) |   | || |    | |       | || |  /  .--.  \  | || |  / .'   \_|  | || |   | |_/ /    | || |  / .'   \_|  | || |   | |__| |   | || |    / /\ \    | || |      | |     | || |  |   \ | |   | |
| |    |  __'.   | || |    | |   _   | || |  | |    | |  | || |  | |         | || |   |  __'.    | || |  | |         | || |   |  __  |   | || |   / ____ \   | || |      | |     | || |  | |\ \| |   | |
| |   _| |__) |  | || |   _| |__/ |  | || |  \  `--'  /  | || |  \ `.___.'\  | || |  _| |  \ \_  | || |  \ `.___.'\  | || |  _| |  | |_  | || | _/ /    \ \_ | || |     _| |_    | || | _| |_\   |_  | |
| |  |_______/   | || |  |________|  | || |   `.____.'   | || |   `._____.'  | || | |____||____| | || |   `._____.'  | || | |____||____| | || ||____|  |____|| || |    |_____|   | || ||_____|\____| | |
| |              | || |              | || |              | || |              | || |              | || |              | || |              | || |              | || |              | || |              | |
| '--------------' || '--------------' || '--------------' || '--------------' || '--------------' || '--------------' || '--------------' || '--------------' || '--------------' || '--------------' |
 '----------------'  '----------------'  '----------------'  '----------------'  '----------------'  '----------------'  '----------------'  '----------------'  '----------------'  '----------------' 
I'm incredibly excited about the future of blockchain technology and its profound impact on the tech industry. I firmly believe that blockchain has the potential to revolutionize the very fabric of the Internet, completely transforming
its underlying infrastructure. The coolest part is that it can seamlessly collaborate and integrate with other cutting-edge technologies like AI, opening up a world of possibilities. Sure, blockchain is still in its early stages, just like
the Internet was back in the '90s. But here's the awesome part: more and more innovators are starting to grasp its hidden power and are working tirelessly to accelerate its development. Blockchain offers us a glimpse into an extraordinary future,
and it's an opportunity for us to come together and be a part of industry-wise transformation. If you want to learn more, check out "Blockchain Revolution" by Don Tapscott. It's an eye-opening read 👀!
```

```haskell
/* Blockchain.hpp:
#include <vector>
#include <memory>
#ifndef Blockchain_H
#define Blockchain_H

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
#endif
*/

#include <iostream>
#include <string>
#include <sstream>
#include <fstream>
#include <algorithm>
#include <iterator>
#include <vector>
#include <memory>
#include <thread>
#include <chrono>
#include <openssl/sha.h>
#include "./headers/timeutils.hpp"
#include "./headers/coinutils.hpp"
#include "./headers/Node.hpp"
#include "./headers/Blockchain.hpp"
#include "./headers/Marketplace.hpp"



// global variables

    /* constants */ 
const uint16_t         gc_NODE_COUNT                         = 15;
const uint16_t         gc_DIFFICULTY                         = 1000;
const uint16_t         gc_INITIAL_AMOUNT                     = gc_NODE_COUNT;
const uint16_t         gc_MAX_TRANSACTION_DATA_SIZE_IN_BYTES = 256;
const uint32_t         gc_TOTAL                              = 21000000;
const float            gc_REWARD                             = 6.25;
const std::string      gc_VOID_HASH                      = "0000000000000000000000000000000000000000000000000000000000000000";
     
    /* non-constants */ 
bool                   g_FINISHED                            = 0;
float                  g_TRANSACTION_FEE;   
float                  g_VALUE;
float                  g_BUY_VALUE;
float                  g_SELL_VALUE;
std::ofstream          logS("./.log");

std::thread g_subsystem(update, &g_TRANSACTION_FEE, &g_VALUE, &g_BUY_VALUE, &g_SELL_VALUE, &g_FINISHED);

...

void Node::closeMyStall(Marketplace& ar_marketplace)
{

    // if node doesn't even have a stall
    if (m_stall == nullptr)
    {

        std::cout << "\nYou don't own a stall, maybe you used to!" << std::endl;
        return;

    }

    // using lambda function with std::find_if() to find position of this node's stall in the market
    std::vector<std::shared_ptr<Stall>>::iterator iter = std::find_if ( ar_marketplace.m_market.begin(), ar_marketplace.m_market.end(),

    [this](const std::shared_ptr<Stall> s) { return (s->mp_seller->m_name == m_name); }

    );

    // delete stall's data from memory
    auto index = (iter - ar_marketplace.m_market.begin()); // get index of found stall in market
    ar_marketplace.m_market[index].reset(); // delete from memory the stall which is pointed to by a shared_pointer
    ar_marketplace.m_market[index] = nullptr;

    // delete stall from market
    ar_marketplace.m_market.erase(iter);

    // finally
    std::cout << "\n--> Stall closed successfully!" << std::endl;

}

...

void Node::transferTo(Blockchain& ar_blockchain, std::vector<std::shared_ptr<Node>>& ar_nodesList, std::string& ar_receiver, const uint32_t& ar_timestamp)
{
    
    // initial checking step
    if (ar_receiver == m_name)
    {
        
        std::cout << "\n->> Can't transfer money to yourserlf you fishing prick!" << std::endl;
        return;

    }

    // transfer money
    float amount;
    bool found = 0;

    for (uint64_t i = 0; i < gc_NODE_COUNT; i++)
    {

        if (ar_nodesList[i]->m_name == ar_receiver)
            found = 1;
            

        if (i == (gc_NODE_COUNT - 1) && found == 0)
        {

            std::cout << "\n->> Node doesn't exit" << std::endl;
            return;

        }

        if (found)
        {
            
            std::cout << "\nEnter the amount of bitcoins to transfer :\n>>> ";
            std::cin >> amount;

            // if not enough bitcoins to transfer
            if (amount > m_balance)
            {

                char option;
                std::cout << "\n->> Your total account balance isn't sufficient for this transfer : " << m_balance << " / " << amount << std::endl;
                std::cout << "Do you want to apply an amount of debt to your account balance? | (Y)es, (N)o\n>>> ";
                std::cin >> option; std::cin.ignore();
                
                if (option == 'y' || option == 'Y')
                {

                    std::cout << "\nAre you sure ? | (Y)es, (N)o\n>>> ";
                    std::cin >> option; std::cin.ignore();

                    if (option == 'y' || option == 'Y')
                    {

                        std::cout << "\n*Sure!" << std::endl;
                        ar_nodesList[i]->m_balance += amount;
                        m_balance -= amount;
                        break;

                    }

                    else
                    {

                        std::cout << "\n*Okay! Abort transaction!" << std::endl;
                        break;

                    }

                }

                else
                {

                    std::cout << "\n*Okay! Abort transaction!" << std::endl;
                    break;

                }
            }
            

            // if enough coins for transferring
            else
            {

                ar_nodesList[i]->m_balance += amount;
                m_balance -= amount;
                break;

            }
            

        }


    }

    // write to public ledger
    std::string tmp = m_name + ' ' + ar_receiver + ' ' + std::to_string(amount) + ' ' + std::to_string(ar_timestamp) + '\n';

    if ( (ar_blockchain.m_tmpTransactionsData.length() + tmp.length()) > gc_MAX_TRANSACTION_DATA_SIZE_IN_BYTES)
    {

        ar_blockchain.openCompetition(tmp, ar_nodesList);

    }

     
    else
    {
        ar_blockchain.m_tmpTransactionsData += tmp;
    }

}

...

void Node::visitStall(Blockchain& ar_blockchain, std::vector<std::shared_ptr<Node>>& ar_nodesList, Marketplace& ar_marketplace, uint64_t& ar_stallNumber)
{

    // initial checking to see if stall exist
    if (ar_stallNumber > ar_marketplace.m_market.size())
    {

        std::cout << "\nStall doesn't exist! Might have bene deleted not long ago!" << std::endl;
        return;

    }

    uint64_t index = ar_stallNumber - 1;
    char option;


    // sellers can't perform  trading with themself
    if (ar_marketplace.m_market[index]->mp_seller->m_name == m_name)
    {

        std::cout << "You can't trade with yourself you fishing prick!" << std::endl;
        return;

    }

    // first and foremost, show stall info
    std::cout << "stall number " << ar_stallNumber << " : " << std::endl;
    std::cout << "\t--> seller : " << ar_marketplace.m_market[index]->mp_seller->m_name << std::endl;

    std::string tmp = (ar_marketplace.m_market[index]->m_type == 0) ? " in exchange of money" : "[USD] in exchange of bitcoins";
    std::cout << "\t--> selling : " << ar_marketplace.m_market[index]->m_amount << tmp << std::endl;

    std::cout << "----------------------------------------------------------------\n";

    // decide whether to take the deal or leave
    std::cout << "seller (" << ar_marketplace.m_market[index]->mp_seller->m_name <<") : '(c)rop or (d)rop buddy?'\n>>> ";
    std::cin >> option; std::cin.ignore();

    if (option == 'c' || option == 'C')
    {
        
        #define focusedStall ar_marketplace.m_market[index] // alias to save writing time
    
        // 0: sell bitcoins for money | 1: sell money for bitcoins
        if (focusedStall->m_type == 0)
        {

            focusedStall->mp_seller->m_balance -= focusedStall->m_amount;
            focusedStall->mp_seller->m_wallet += (focusedStall->m_amount * g_SELL_VALUE);

            m_balance += focusedStall->m_amount;
            m_wallet -= (focusedStall->m_amount * g_BUY_VALUE);
            
            // data to be written to public ledger, trading is technically transferring
            // <from> <to> <amount>
            tmp = focusedStall->mp_seller->m_name + ' ' + m_name + ' ' + std::to_string(focusedStall->m_amount) + ' ' + std::to_string(time(0)) + '\n';

        }

        else
        {

            double excess = fmod(focusedStall->mp_seller->m_wallet, g_BUY_VALUE); // left-over money
            float tradableBitcoins = (focusedStall->m_amount / g_BUY_VALUE);

            focusedStall->mp_seller->m_wallet -= (focusedStall->m_amount - excess);
            focusedStall->mp_seller->m_balance += (tradableBitcoins);

            m_wallet += ( (focusedStall->m_amount / g_SELL_VALUE) * g_SELL_VALUE);
            m_balance -= tradableBitcoins;

            // data to be written to public ledger, trading is technically trasnfering
            // <from> <to> <amount>
            tmp =  m_name + ' ' + focusedStall->mp_seller->m_name + ' ' + std::to_string(focusedStall->m_amount) + ' ' + std::to_string(time(0)) + '\n';
        }

        //write to public ledger, trading is technically trasnfering
        if ( (ar_blockchain.m_tmpTransactionsData.length() + tmp.length()) > gc_MAX_TRANSACTION_DATA_SIZE_IN_BYTES)
        {

            ar_blockchain.openCompetition(tmp, ar_nodesList);

        }

        else
        {

            ar_blockchain.m_tmpTransactionsData += tmp;

        }

        
        ar_marketplace.m_market[index]->mp_seller->closeMyStall(ar_marketplace); // force the stall owner to close stall as trade complete; 
        storeOurCoins(ar_nodesList);        // saving
        storeOurWallets(ar_nodesList);     // saving

        std::cout << "\n--> Trading complete! Have a great day!" << std::endl;
        return;

    }

    else if (option == 'd' || option == 'D')
    {

        std::cout << "\n-->Understandable, have a great day!" << std::endl;
        return;

    }

    else 
    {
        std::cout << "Option invalid : " << option << std::endl;
        return;
    }


}

...

void Marketplace::showAllStalls()
{

    uint64_t i = 0;
    std::string tmp;
    
    std::cout << "----------------------------------------------------------------\n";
    for (const auto& s : m_market)
    {

        std::cout << "stall number " << i + 1 << " : " << std::endl;
        std::cout << "\t--> seller : " << s->mp_seller->m_name << std::endl;

        tmp = (s->m_type == 0) ? " bitcoins in exchange of money" : "[USD] in exchange of bitcoins";
        std::cout << "\t--> selling : " << s->m_amount << tmp << std::endl;

        std::cout << "----------------------------------------------------------------\n";

        ++i;

    }
    
}

...
*Caution: this piece of code isn't functional, it's just for demonstration purpose :)
```

<p align="center">
  <img src="https://github.com/ducmint864/Gifs/blob/main/HmsT9Zzmvu4EDQS75P.gif" alt="Your GIF" width="100%">
</p>


<p align="center">
  <img src="https://github.com/ducmint864/Gifs/blob/main/8COxPYplWmHKlZULOt.gif" alt="Your GIF" width="100%">
</p>

<p align="center">
  <img src="https://github.com/ducmint864/Gifs/blob/main/l0MYLJhlwdLh9uPeg.gif" alt="Your GIF" width="100%">
</p>

### How would you imagine the future?



### About me
- 🔭 I’m enthusiastic in: Linux, Cloud, big data, web development(including Web3), defi, smart contract development
- 🌱 I’m currently learning blockchain and smart contract development
- 👯 I’m looking for passionate people to learn from and collab with
- 🤔 I’m looking for help with ...
- ⚡ Knowledge: C/C++, Javascript, Solidity, Python, Linux
```python
  ________  ________    ________      _________ __________  ___________ ___________ ________            
 /  _____/  \_____  \   \______ \    /   _____/ \______   \ \_   _____/ \_   _____/ \______ \    /\  /\ 
/   \  ___   /   |   \   |    |  \   \_____  \   |     ___/  |    __)_   |    __)_   |    |  \   \/  \/ 
\    \_\  \ /    |    \  |    `   \  /        \  |    |      |        \  |        \  |    `   \  /\  /\ 
 \______  / \_______  / /_______  / /_______  /  |____|     /_______  / /_______  / /_______  /  \/  \/ 
        \/          \/          \/          \/                      \/          \/          \/          
```
<p align="center">
  <img src="https://github.com/ducmint864/Gifs/blob/main/cSdSijzwrsliuI1hnC.gif" alt="Your GIF" width="100%">
</p>

<p align="center">
  <img src="https://github.com/ducmint864/Gifs/blob/main/3o6ZtcYOStjD2SkMuY.gif" alt="Your GIF" width="100%">
</p>

<p align="center">
  <img src="https://github.com/ducmint864/Gifs/blob/main/wHfBl3XNAcxxj0JOk8.gif" alt="Your GIF" width="100%">
</p>

<p align="center">
  <img src="https://github.com/ducmint864/Gifs/blob/main/w61NUc9wVBAZi5PUOY.gif" alt="Your GIF" width="100%">
</p>

<p align="center">
  <img src="https://github.com/ducmint864/Gifs/blob/main/3oKIPs1EVbbNZYq7EA.gif" alt="Your GIF" width="100%">
</p>
