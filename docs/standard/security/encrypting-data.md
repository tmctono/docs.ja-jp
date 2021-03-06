---
title: データの暗号化
description: 対称アルゴリズムまたは非対称アルゴリズムを使用して、.NET でデータを暗号化する方法について説明します。
ms.date: 07/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encryption [.NET], symmetric
- symmetric encryption
- cryptography [.NET], asymmetric
- asymmetric encryption
ms.assetid: 7ecce51f-db5f-4bd4-9321-cceb6fcb2a77
ms.openlocfilehash: 8a8b5988a13ab571284b08c7aaece3542467aa71
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556970"
---
# <a name="encrypting-data"></a>データの暗号化

対称暗号化と非対称暗号化は、異なるプロセスを使用して実行されます。 対称暗号化は、ストリーム上で実行されるため、大量のデータの暗号化に役立ちます。 非対称暗号化は、少ないバイト数で実行されるため、少量のデータにのみ役立ちます。  
  
## <a name="symmetric-encryption"></a>対称暗号化  

マネージド対称暗号化クラスは、ストリームに読み取られるデータを暗号化する <xref:System.Security.Cryptography.CryptoStream> という特別なストリーム クラスと共に使用されます。 **Cryptostream**クラスは、マネージストリームクラス、インターフェイスを実装するクラス <xref:System.Security.Cryptography.ICryptoTransform> (暗号アルゴリズムを実装するクラスから作成)、および <xref:System.Security.Cryptography.CryptoStreamMode> **cryptostream**に許可されているアクセスの種類を記述する列挙体を使用して初期化されます。 **CryptoStream**クラスは、クラスから派生した任意のクラス (、、など) を使用して初期化でき <xref:System.IO.Stream> <xref:System.IO.FileStream> <xref:System.IO.MemoryStream> <xref:System.Net.Sockets.NetworkStream> ます。 これらのクラスを使用すると、さまざまなストリーム オブジェクトの対称暗号化を実行できます。  
  
次の例は、アルゴリズムの既定の実装クラスの新しいインスタンスを作成する方法を示してい <xref:System.Security.Cryptography.Aes> ます。 インスタンスは、 **CryptoStream**クラスで暗号化を実行するために使用されます。 この例では、 **CryptoStream** は `myStream` と呼ばれるストリーム オブジェクトで初期化されています。これは任意の種類のマネージド ストリームにすることができます。 **Aes**クラスの**createencryptor**メソッドには、暗号化に使用されるキーと IV が渡されます。 この場合、 `aes` から生成された既定のキーと IV が使用されます。
  
```vb  
Dim aes As Aes = Aes.Create()  
Dim cryptStream As New CryptoStream(myStream, aes.CreateEncryptor(key, iv), CryptoStreamMode.Write)  
```  
  
```csharp  
Aes aes = Aes.Create();  
CryptoStream cryptStream = new CryptoStream(myStream, aes.CreateEncryptor(key, iv), CryptoStreamMode.Write);  
```  
  
このコードを実行すると、 **CryptoStream**オブジェクトに書き込まれたデータは、AES アルゴリズムを使用して暗号化されます。  
  
次の例は、ストリームの作成、ストリームの暗号化、ストリームへの書き込み、およびストリームを閉じるプロセス全体を示しています。 この例では、 **CryptoStream**クラスと**Aes**クラスを使用して暗号化されたファイルストリームを作成します。 <xref:System.IO.StreamWriter> クラスを使用して、暗号化されたストリームにメッセージが書き込まれます。
  
:::code language="csharp" source="snippets/encrypting-data/csharp/aes-encrypt.cs":::
:::code language="vb" source="snippets/encrypting-data/vb/aes-encrypt.vb":::

このコードは、AES 対称アルゴリズムを使用してストリームを暗号化し、"Hello World!" を書き込みます。 ストリームに書き込みます。 コードが正常に実行されると、 *TestData.txt*という名前の暗号化されたファイルが作成され、次のテキストがコンソールに表示されます。  
  
```console  
The text was encrypted.  
```  

ファイルの暗号化を解除するには、[データ](decrypting-data.md)の暗号化解除の対称復号化の例を使用します。 この例とこの例では、同じキーと IV を指定しています。

ただし、例外が発生した場合、コードは次のテキストをコンソールに表示します。  
  
```console  
The encryption failed.  
```

## <a name="asymmetric-encryption"></a>非対称暗号化

非対称アルゴリズムは、通常は対称キーと IV の暗号化など、少量のデータの暗号化に使用されます。 通常、非対称暗号化を行う個人や組織は、別のパーティによって生成された公開キーを使用します。 クラスは、 <xref:System.Security.Cryptography.RSA> この目的のために .net によって提供されます。  
  
次の例では、公開キーの情報を使用して対称キーと IV を暗号化します。 サード パーティの公開キーを表す 2 つのバイト配列が初期化されます。 <xref:System.Security.Cryptography.RSAParameters> オブジェクトがこれらの値に初期化されます。 次に、 **RSAParameters**オブジェクト (それが表す公開キー) を、メソッドを使用して**RSA**インスタンスにインポートし <xref:System.Security.Cryptography.RSA.ImportParameters%2A?displayProperty=nameWithType> ます。 最後に、クラスによって作成された秘密キーと IV <xref:System.Security.Cryptography.Aes> が暗号化されます。 この例では、システムに 128 ビット暗号化がインストールされている必要があります。  
  
```vb  
Imports System
Imports System.Security.Cryptography

Module Module1

    Sub Main()
        'Initialize the byte arrays to the public key information.  
        Dim modulus As Byte() = {214, 46, 220, 83, 160, 73, 40, 39, 201, 155, 19, 202, 3, 11, 191, 178, 56, 74, 90, 36, 248, 103, 18, 144, 170, 163, 145, 87, 54, 61, 34, 220, 222, 207, 137, 149, 173, 14, 92, 120, 206, 222, 158, 28, 40, 24, 30, 16, 175, 108, 128, 35, 230, 118, 40, 121, 113, 125, 216, 130, 11, 24, 90, 48, 194, 240, 105, 44, 76, 34, 57, 249, 228, 125, 80, 38, 9, 136, 29, 117, 207, 139, 168, 181, 85, 137, 126, 10, 126, 242, 120, 247, 121, 8, 100, 12, 201, 171, 38, 226, 193, 180, 190, 117, 177, 87, 143, 242, 213, 11, 44, 180, 113, 93, 106, 99, 179, 68, 175, 211, 164, 116, 64, 148, 226, 254, 172, 147}

        Dim exponent As Byte() = {1, 0, 1}

        'Create values to store encrypted symmetric keys.  
        Dim encryptedSymmetricKey() As Byte
        Dim encryptedSymmetricIV() As Byte

        'Create a new instance of the default RSA implementation class.
        Dim rsa As RSA = RSA.Create()

        'Create a new instance of the RSAParameters structure.  
        Dim rsaKeyInfo As New RSAParameters()

        'Set rsaKeyInfo to the public key values.
        rsaKeyInfo.Modulus = modulus
        rsaKeyInfo.Exponent = exponent

        'Import key parameters into rsa
        rsa.ImportParameters(rsaKeyInfo)

        'Create a new instance of the default Aes implementation class.  
        Dim aes As Aes = Aes.Create()

        'Encrypt the symmetric key and IV.  
        encryptedSymmetricKey = rsa.Encrypt(aes.Key, RSAEncryptionPadding.Pkcs1)
        encryptedSymmetricIV = rsa.Encrypt(aes.IV, RSAEncryptionPadding.Pkcs1)
    End Sub

End Module
```  
  
```csharp  
using System;
using System.Security.Cryptography;

class Class1
{
    static void Main()
    {
        //Initialize the byte arrays to the public key information.  
        byte[] modulus = {214,46,220,83,160,73,40,39,201,155,19,202,3,11,191,178,56,
            74,90,36,248,103,18,144,170,163,145,87,54,61,34,220,222,
            207,137,149,173,14,92,120,206,222,158,28,40,24,30,16,175,
            108,128,35,230,118,40,121,113,125,216,130,11,24,90,48,194,
            240,105,44,76,34,57,249,228,125,80,38,9,136,29,117,207,139,
            168,181,85,137,126,10,126,242,120,247,121,8,100,12,201,171,
            38,226,193,180,190,117,177,87,143,242,213,11,44,180,113,93,
            106,99,179,68,175,211,164,116,64,148,226,254,172,147};

        byte[] exponent = { 1, 0, 1 };

        //Create values to store encrypted symmetric keys.  
        byte[] encryptedSymmetricKey;
        byte[] encryptedSymmetricIV;

        //Create a new instance of the RSA class.  
        RSA rsa = RSA.Create();

        //Create a new instance of the RSAParameters structure.  
        RSAParameters rsaKeyInfo = new RSAParameters();

        //Set rsaKeyInfo to the public key values.
        rsaKeyInfo.Modulus = modulus;
        rsaKeyInfo.Exponent = exponent;

        //Import key parameters into rsa.  
        rsa.ImportParameters(rsaKeyInfo);

        //Create a new instance of the default Aes implementation class.  
        Aes aes = Aes.Create();

        //Encrypt the symmetric key and IV.  
        encryptedSymmetricKey = rsa.Encrypt(aes.Key, RSAEncryptionPadding.Pkcs1);
        encryptedSymmetricIV = rsa.Encrypt(aes.IV, RSAEncryptionPadding.Pkcs1);
    }
}
```  
  
## <a name="see-also"></a>関連項目

- [暗号化と復号化のためのキーの生成](generating-keys-for-encryption-and-decryption.md)
- [データの復号化](decrypting-data.md)
- [Cryptographic Services](cryptographic-services.md)
- [クロスプラットフォーム暗号化](cross-platform-cryptography.md)
- [パディングを使用した CBC モードの対称復号化に関するタイミングの脆弱性](vulnerabilities-cbc-mode.md)
- [データ保護の ASP.NET Core](/aspnet/core/security/data-protection/introduction)
