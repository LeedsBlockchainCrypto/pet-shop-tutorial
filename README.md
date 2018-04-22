# pet-shop-tutorial

http://truffleframework.com/tutorials/pet-shop

I had to modify app.js
'''
initWeb3: function() {
    // Is there an injected web3 instance?
    if (typeof web3 !== 'undefined') {
      App.web3Provider = web3.currentProvider;
    } else {
      // If no injected web3 instance is detected, fall back to Ganache
      App.web3Provider = new Web3.providers.HttpProvider('http://localhost:7545');
    }
    web3 = new Web3(App.web3Provider);
    return App.initContract();
  },
'''
to
'''
initWeb3: function() {  
    // Is there an injected web3 instance?
    // If no injected web3 instance is detected, fall back to Ganache
    App.web3Provider = new Web3.providers.HttpProvider('http://localhost:7545');
   
    web3 = new Web3(App.web3Provider);

    return App.initContract();
  },
'''  
For some reason it wasn't picking up gnache as a provider
  
Also I do not get a prompt from metamask asking me to confirm the adoption. This could be down to my confirguration. I haven't had a chance to work through why
