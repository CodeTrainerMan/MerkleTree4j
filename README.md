## MerkleTree4j
<p align="center">
    <img src="https://img.shields.io/badge/JDK-1.8+-green.svg">
</p>

this project use web3utils publish package,that my project too. this merkletree result is same result whit solidity merkle result;

#start:  add jar in pom.xml

        <dependency>
                <groupId>io.github.CodeTrainerMan</groupId>
                <artifactId>web3utils</artifactId>
                <version>1.0.1</version>
        </dependency>
 
 #test:
 
        List<String> list = new ArrayList<>();
        list.add(packedKeccak256("0xfc3921042358aC9a4092C4506bD20C6d9744DA47",981));
        list.add(packedKeccak256("0x5d46Cc7813E97AC4379df8c1Fe30B8c875754aa0",711));
        list.add(packedKeccak256("0x9F7827F2EeD4E608d22057e03d6aAe593F0e47ae",9));
        list.add(packedKeccak256("0xA76f2B935C04Ab0D1c2EB16a4A7f410C656Cf645",1));
        list.add(packedKeccak256("0x5484B2df5674e2E3F9954C3972774fd2bF0A5326",170));
        list.add(packedKeccak256("0x03a6dfE7c7AA062F23B56657313571cD1CD4aDf9",1057));

        MerkleTree merkleTree = new MerkleTree(list, true);
        List<String> proof = merkleTree4Solidity.getProof(packedKeccak256("0xfc3921042358aC9a4092C4506bD20C6d9744DA47",981), null);
        String root = merkleTree4Solidity.getRoot();
        boolean verify = merkleTree4Solidity.verify(proof, root, packedKeccak256("0xfc3921042358aC9a4092C4506bD20C6d9744DA47",981));
        System.out.println(list);
