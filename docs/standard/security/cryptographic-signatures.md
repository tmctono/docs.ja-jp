---
title: 暗号署名
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- digital signatures
- cryptography [.NET Framework], signatures
- digital signatures, XML signing
- signatures, cryptographic
- digital signatures, generating
- verifying signatures
- generating signatures
- digital signatures, about
- encryption [.NET Framework], signatures
- security [.NET Framework], signatures
- XML signing
- digital signatures, verifying
- signing XML
ms.assetid: aa87cb7f-e608-4a81-948b-c9b8a1225783
author: mairaw
ms.author: mairaw
ms.openlocfilehash: de64af1a4617af39b0ef8e054292a402d6a145e6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350458"
---
# <a name="cryptographic-signatures"></a><span data-ttu-id="9352a-102">暗号署名</span><span class="sxs-lookup"><span data-stu-id="9352a-102">Cryptographic Signatures</span></span>

<span data-ttu-id="9352a-103">暗号デジタル署名は、公開キー アルゴリズムを使用してデータの整合性を提供します。</span><span class="sxs-lookup"><span data-stu-id="9352a-103">Cryptographic digital signatures use public key algorithms to provide data integrity.</span></span> <span data-ttu-id="9352a-104">デジタル署名を使用してデータに署名すると、第三者が署名を検証し、データが署名者から発信され、署名後に変更されていないことを証明できます。</span><span class="sxs-lookup"><span data-stu-id="9352a-104">When you sign data with a digital signature, someone else can verify the signature, and can prove that the data originated from you and was not altered after you signed it.</span></span> <span data-ttu-id="9352a-105">デジタル署名の詳細については、「 [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9352a-105">For more information about digital signatures, see [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md).</span></span>

<span data-ttu-id="9352a-106">ここでは、 <xref:System.Security.Cryptography?displayProperty=nameWithType> 名前空間のクラスを使用してデジタル署名を生成して検証する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9352a-106">This topic explains how to generate and verify digital signatures using classes in the <xref:System.Security.Cryptography?displayProperty=nameWithType> namespace.</span></span>

## <a name="generating-signatures"></a><span data-ttu-id="9352a-107">署名の生成</span><span class="sxs-lookup"><span data-stu-id="9352a-107">Generating Signatures</span></span>

<span data-ttu-id="9352a-108">デジタル署名は、通常、大きなデータを表現するハッシュ値に適用されます。</span><span class="sxs-lookup"><span data-stu-id="9352a-108">Digital signatures are usually applied to hash values that represent larger data.</span></span> <span data-ttu-id="9352a-109">ハッシュ値にデジタル署名を適用する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9352a-109">The following example applies a digital signature to a hash value.</span></span> <span data-ttu-id="9352a-110">まず、 <xref:System.Security.Cryptography.RSACryptoServiceProvider> クラスの新しいインスタンスを作成して、公開キー/秘密キーのペアを生成します。</span><span class="sxs-lookup"><span data-stu-id="9352a-110">First, a new instance of the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class is created to generate a public/private key pair.</span></span> <span data-ttu-id="9352a-111">次に、 <xref:System.Security.Cryptography.RSACryptoServiceProvider> を <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> クラスの新しいインスタンスに渡します。</span><span class="sxs-lookup"><span data-stu-id="9352a-111">Next, the <xref:System.Security.Cryptography.RSACryptoServiceProvider> is passed to a new instance of the <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> class.</span></span> <span data-ttu-id="9352a-112">これにより、デジタル署名を実際に実行する <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter>に秘密キーが渡されます。</span><span class="sxs-lookup"><span data-stu-id="9352a-112">This transfers the private key to the <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter>, which actually performs the digital signing.</span></span> <span data-ttu-id="9352a-113">ハッシュ コードに署名するためには、使用するハッシュ アルゴリズムを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9352a-113">Before you can sign the hash code, you must specify a hash algorithm to use.</span></span> <span data-ttu-id="9352a-114">この例では、SHA1 アルゴリズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="9352a-114">This example uses the SHA1 algorithm.</span></span> <span data-ttu-id="9352a-115">最後に、 <xref:System.Security.Cryptography.AsymmetricSignatureFormatter.CreateSignature%2A> メソッドを呼び出して署名を実行します。</span><span class="sxs-lookup"><span data-stu-id="9352a-115">Finally, the <xref:System.Security.Cryptography.AsymmetricSignatureFormatter.CreateSignature%2A> method is called to perform the signing.</span></span>

<span data-ttu-id="9352a-116">Due to collision problems with SHA1, Microsoft recommends SHA256 or better.</span><span class="sxs-lookup"><span data-stu-id="9352a-116">Due to collision problems with SHA1, Microsoft recommends SHA256 or better.</span></span>

```vb
Imports System.Security.Cryptography

Module Module1
    Sub Main()
        'The hash value to sign.
        Dim hashValue As Byte() = {59, 4, 248, 102, 77, 97, 142, 201, 210, 12, 224, 93, 25, 41, 100, 197, 213, 134, 130, 135}

        'The value to hold the signed value.
        Dim signedHashValue() As Byte

        'Generate a public/private key pair.
        Dim rsa As New RSACryptoServiceProvider()

        'Create an RSAPKCS1SignatureFormatter object and pass it
        'the RSACryptoServiceProvider to transfer the private key.
        Dim rsaFormatter As New RSAPKCS1SignatureFormatter(rsa)

        'Set the hash algorithm to SHA1.
        rsaFormatter.SetHashAlgorithm("SHA1")

        'Create a signature for hashValue and assign it to
        'signedHashValue.
        signedHashValue = rsaFormatter.CreateSignature(hashValue)
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
      //The hash value to sign.
      byte[] hashValue = {59,4,248,102,77,97,142,201,210,12,224,93,25,41,100,197,213,134,130,135};

      //The value to hold the signed value.
      byte[] signedHashValue;

      //Generate a public/private key pair.
      RSACryptoServiceProvider rsa = new RSACryptoServiceProvider();

      //Create an RSAPKCS1SignatureFormatter object and pass it the
      //RSACryptoServiceProvider to transfer the private key.
      RSAPKCS1SignatureFormatter rsaFormatter = new RSAPKCS1SignatureFormatter(rsa);

      //Set the hash algorithm to SHA1.
      rsaFormatter.SetHashAlgorithm("SHA1");

      //Create a signature for hashValue and assign it to
      //signedHashValue.
      signedHashValue = rsaFormatter.CreateSignature(hashValue);
   }
}
```

### <a name="signing-xml-files"></a><span data-ttu-id="9352a-117">XML ファイルへの署名</span><span class="sxs-lookup"><span data-stu-id="9352a-117">Signing XML Files</span></span>

<span data-ttu-id="9352a-118">.NET Framework に用意されている <xref:System.Security.Cryptography.Xml> 名前空間を使用すると、XML に署名できます。</span><span class="sxs-lookup"><span data-stu-id="9352a-118">The .NET Framework provides the <xref:System.Security.Cryptography.Xml> namespace, which enables you sign XML.</span></span> <span data-ttu-id="9352a-119">XML が特定のソースから送信されたことを検証する場合は、XML への署名が重要です。</span><span class="sxs-lookup"><span data-stu-id="9352a-119">Signing XML is important when you want to verify that the XML originates from a certain source.</span></span> <span data-ttu-id="9352a-120">たとえば、XML を使用する株価情報サービスを使用している場合であれば、署名されているかどうかによって XML のソースを検証できます。</span><span class="sxs-lookup"><span data-stu-id="9352a-120">For example, if you are using a stock quote service that uses XML, you can verify the source of the XML if it is signed.</span></span>

<span data-ttu-id="9352a-121">この名前空間のクラスは、World Wide Web コンソーシアムの「 [XML 署名の構文と処理に関する勧告](https://www.w3.org/TR/xmldsig-core/) 」に従っています。</span><span class="sxs-lookup"><span data-stu-id="9352a-121">The classes in this namespace follow the [XML-Signature Syntax and Processing recommendation](https://www.w3.org/TR/xmldsig-core/) from the World Wide Web Consortium.</span></span>

## <a name="verifying-signatures"></a><span data-ttu-id="9352a-122">署名の検証</span><span class="sxs-lookup"><span data-stu-id="9352a-122">Verifying Signatures</span></span>

<span data-ttu-id="9352a-123">データが特定の関係者によって署名されたことを検証するには、次の情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="9352a-123">To verify that data was signed by a particular party, you must have the following information:</span></span>

- <span data-ttu-id="9352a-124">データに署名した関係者の公開キー。</span><span class="sxs-lookup"><span data-stu-id="9352a-124">The public key of the party that signed the data.</span></span>

- <span data-ttu-id="9352a-125">デジタル署名。</span><span class="sxs-lookup"><span data-stu-id="9352a-125">The digital signature.</span></span>

- <span data-ttu-id="9352a-126">署名されたデータ。</span><span class="sxs-lookup"><span data-stu-id="9352a-126">The data that was signed.</span></span>

- <span data-ttu-id="9352a-127">署名者が使用したハッシュ アルゴリズム。</span><span class="sxs-lookup"><span data-stu-id="9352a-127">The hash algorithm used by the signer.</span></span>

<span data-ttu-id="9352a-128"><xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> クラスによって署名された署名を検証するには、 <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="9352a-128">To verify a signature signed by the <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> class, use the <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> class.</span></span> <span data-ttu-id="9352a-129"><xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> クラスに対しては、署名者の公開キーを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9352a-129">The <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> class must be supplied the public key of the signer.</span></span> <span data-ttu-id="9352a-130">公開キーを指定するには、剰余値と指数部の値が必要になります</span><span class="sxs-lookup"><span data-stu-id="9352a-130">You will need the values of the modulus and the exponent to specify the public key.</span></span> <span data-ttu-id="9352a-131">(The party that generated the public/private key pair should provide these values.) First create an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to hold the public key that will verify the signature, and then initialize an <xref:System.Security.Cryptography.RSAParameters> structure to the modulus and exponent values that specify the public key.</span><span class="sxs-lookup"><span data-stu-id="9352a-131">(The party that generated the public/private key pair should provide these values.) First create an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to hold the public key that will verify the signature, and then initialize an <xref:System.Security.Cryptography.RSAParameters> structure to the modulus and exponent values that specify the public key.</span></span>

<span data-ttu-id="9352a-132">次のコードは、 <xref:System.Security.Cryptography.RSAParameters> 構造体の作成を示しています。</span><span class="sxs-lookup"><span data-stu-id="9352a-132">The following code shows the creation of an <xref:System.Security.Cryptography.RSAParameters> structure.</span></span> <span data-ttu-id="9352a-133">`Modulus` プロパティは `modulusData` というバイト配列の値に設定し、 `Exponent` プロパティは `exponentData`というバイト配列の値に設定します。</span><span class="sxs-lookup"><span data-stu-id="9352a-133">The `Modulus` property is set to the value of a byte array called `modulusData` and the `Exponent` property is set to the value of a byte array called `exponentData`.</span></span>

```vb
Dim rsaKeyInfo As RSAParameters
rsaKeyInfo.Modulus = modulusData
rsaKeyInfo.Exponent = exponentData
```

```csharp
RSAParameters rsaKeyInfo;
rsaKeyInfo.Modulus = modulusData;
rsaKeyInfo.Exponent = exponentData;
```

<span data-ttu-id="9352a-134"><xref:System.Security.Cryptography.RSAParameters> オブジェクトを作成した後、 <xref:System.Security.Cryptography.RSACryptoServiceProvider> クラスの新しいインスタンスを <xref:System.Security.Cryptography.RSAParameters>で指定した値に初期設定できます。</span><span class="sxs-lookup"><span data-stu-id="9352a-134">After you have created the <xref:System.Security.Cryptography.RSAParameters> object, you can initialize a new instance of the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class to the values specified in <xref:System.Security.Cryptography.RSAParameters>.</span></span> <span data-ttu-id="9352a-135">次に、 <xref:System.Security.Cryptography.RSACryptoServiceProvider> を <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> のコンストラクターに渡してキーを転送します。</span><span class="sxs-lookup"><span data-stu-id="9352a-135">The <xref:System.Security.Cryptography.RSACryptoServiceProvider> is, in turn, passed to the constructor of an <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> to transfer the key.</span></span>

<span data-ttu-id="9352a-136">このプロセスを説明する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9352a-136">The following example illustrates this process.</span></span> <span data-ttu-id="9352a-137">この例で、 `hashValue` と `signedHashValue` は、リモートにいる関係者から提供されるバイト配列です。</span><span class="sxs-lookup"><span data-stu-id="9352a-137">In this example, `hashValue` and `signedHashValue` are arrays of bytes provided by a remote party.</span></span> <span data-ttu-id="9352a-138">リモートにいる関係者は、SHA1 アルゴリズムを使用して `hashValue` に署名し、デジタル署名 `signedHashValue`を生成します。</span><span class="sxs-lookup"><span data-stu-id="9352a-138">The remote party has signed the `hashValue` using the SHA1 algorithm, producing the digital signature `signedHashValue`.</span></span> <span data-ttu-id="9352a-139">The <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter.VerifySignature%2A?displayProperty=nameWithType> method verifies that the digital signature is valid and was used to sign the `hashValue`.</span><span class="sxs-lookup"><span data-stu-id="9352a-139">The <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter.VerifySignature%2A?displayProperty=nameWithType> method verifies that the digital signature is valid and was used to sign the `hashValue`.</span></span>

```vb
Dim rsa As New RSACryptoServiceProvider()
rsa.ImportParameters(rsaKeyInfo)
Dim rsaDeformatter As New RSAPKCS1SignatureDeformatter(rsa)
rsaDeformatter.SetHashAlgorithm("SHA1")
If rsaDeformatter.VerifySignature(hashValue, signedHashValue) Then
   Console.WriteLine("The signature is valid.")
Else
   Console.WriteLine("The signature is not valid.")
End If
```

```csharp
RSACryptoServiceProvider rsa = new RSACryptoServiceProvider();
rsa.ImportParameters(rsaKeyInfo);
RSAPKCS1SignatureDeformatter rsaDeformatter = new RSAPKCS1SignatureDeformatter(rsa);
rsaDeformatter.SetHashAlgorithm("SHA1");
if(rsaDeformatter.VerifySignature(hashValue, signedHashValue))
{
   Console.WriteLine("The signature is valid.");
}
else
{
   Console.WriteLine("The signature is not valid.");
}
```

<span data-ttu-id="9352a-140">上記のコードでは、署名が有効であれば "`The signature is valid`" を表示し、署名が無効であれば "`The signature is not valid`" を表示します。</span><span class="sxs-lookup"><span data-stu-id="9352a-140">This code fragment will display "`The signature is valid`" if the signature is valid and "`The signature is not valid`" if it is not.</span></span>

## <a name="see-also"></a><span data-ttu-id="9352a-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="9352a-141">See also</span></span>

- [<span data-ttu-id="9352a-142">暗号サービス</span><span class="sxs-lookup"><span data-stu-id="9352a-142">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
