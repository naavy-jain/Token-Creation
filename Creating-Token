// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
*/

contract MyToken {

    // public variables here
string public tokenName = "Meta";
    string public tokenAbbrv = "met";
    uint public totalSupply = 0;

    // mapping variable here
mapping(address => uint) public balances;
    
    event TokensMinted(address indexed account, uint amount);
    event TokensBurned(address indexed account, uint amount);

    modifier onlyOwner() {
        require(msg.sender == owner, "Only the owner can call this function");
        _;
    }

    address public owner;

    constructor() {
        owner = msg.sender;
    }

    // mint function
	function mint(address _address, uint _value) public onlyOwner {
        require(_value > 0, "Mint value must be greater than 0");
        
        totalSupply += _value;
        balances[_address] += _value;
        
        emit TokensMinted(_address, _value);
    }
    // burn function
	function burn(address _address, uint _value) public onlyOwner {
        require(_value > 0, "Burn value must be greater than 0");
        require(balances[_address] >= _value, "Insufficient balance");

        totalSupply -= _value;
        balances[_address] -= _value;

        emit TokensBurned(_address, _value);
}
}
