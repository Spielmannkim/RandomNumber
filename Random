// SPDX-License-Identifier: MIT

pragma solidity ^0.8.7;

import "./VRFv2Consumer.sol";

contract Random {

    VRFv2Consumer public contractA;
    function setContract(address _otherContract) external {
        contractA = VRFv2Consumer(_otherContract);
    }

    function getRandom() external {
        contractA.requestRandomWords();
    }

    function getRequestId() external view returns(uint) {
        return contractA.lastRequestId();
    }

    function getRandomValues(uint _requestId) external view returns (bool fulfilled, uint256[] memory randomWords) {
        (fulfilled, randomWords) = contractA.getRequestStatus(_requestId);
    }

    function getRandomNumber(uint _requestId) external view returns (uint) {
        (, uint256[] memory randomWords) = contractA.getRequestStatus(_requestId);
        return randomWords[0];
    }

    function getMod(uint _requestId) external view returns (uint) {
        (, uint256[] memory randomWords) = contractA.getRequestStatus(_requestId);
        return randomWords[0] % 500;
    }

}
