// SPDX-License-Identifier: MIT
pragma solidity ^0.8.26;

contract Itachitoken {
    string public name = "ItachiToken";
    string public symbol = "ITT";
    uint256 public totalSupply;
    mapping(address => uint256) public balanceOf;

    constructor(uint256 initialSupply) {
        totalSupply = initialSupply;
        balanceOf[msg.sender] = initialSupply;

    }
    function transfer(address toWhom, uint256 value) public returns (bool success){
        require(balanceOf[msg.sender] >= value, "Insufficient tokens, soz");
        balanceOf[msg.sender] -= value;
        balanceOf[toWhom] += value;
        return true;
    }
    
}
