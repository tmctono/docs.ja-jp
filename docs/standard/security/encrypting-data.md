---
title: データの暗号化
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encryption [.NET Framework], symmetric
- symmetric encryption
- cryptography [.NET Framework], asymmetric
- asymmetric encryption
ms.assetid: 7ecce51f-db5f-4bd4-9321-cceb6fcb2a77
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d37f7980c3024fa545e5395a4614dcd41a111794
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "71353194"
---
# <a name="encrypting-data"></a><span data-ttu-id="1dafb-102">データの暗号化</span><span class="sxs-lookup"><span data-stu-id="1dafb-102">Encrypting Data</span></span>
<span data-ttu-id="1dafb-103">対称暗号化と非対称暗号化は、異なるプロセスを使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="1dafb-103">Symmetric encryption and asymmetric encryption are performed using different processes.</span></span> <span data-ttu-id="1dafb-104">対称暗号化は、ストリーム上で実行されるため、大量のデータの暗号化に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1dafb-104">Symmetric encryption is performed on streams and is therefore useful to encrypt large amounts of data.</span></span> <span data-ttu-id="1dafb-105">非対称暗号化は、少ないバイト数で実行されるため、少量のデータにのみ役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1dafb-105">Asymmetric encryption is performed on a small number of bytes and is therefore useful only for small amounts of data.</span></span>  
  
## <a name="symmetric-encryption"></a><span data-ttu-id="1dafb-106">対称暗号化</span><span class="sxs-lookup"><span data-stu-id="1dafb-106">Symmetric Encryption</span></span>  
 <span data-ttu-id="1dafb-107">マネージド対称暗号化クラスは、ストリームに読み取られるデータを暗号化する <xref:System.Security.Cryptography.CryptoStream> という特別なストリーム クラスと共に使用されます。</span><span class="sxs-lookup"><span data-stu-id="1dafb-107">The managed symmetric cryptography classes are used with a special stream class called a <xref:System.Security.Cryptography.CryptoStream> that encrypts data read into the stream.</span></span> <span data-ttu-id="1dafb-108">**CryptoStream** クラスは、マネージド ストリーム クラスを使用して初期化されます。クラスは、(暗号化アルゴリズムを実装するクラスから作成された) <xref:System.Security.Cryptography.ICryptoTransform> インターフェイス、および <xref:System.Security.Cryptography.CryptoStreamMode> CryptoStream **に対して許可されたアクセスの種類について記述した**列挙体を実装します。</span><span class="sxs-lookup"><span data-stu-id="1dafb-108">The **CryptoStream** class is initialized with a managed stream class, a class implements the <xref:System.Security.Cryptography.ICryptoTransform> interface (created from a class that implements a cryptographic algorithm), and a <xref:System.Security.Cryptography.CryptoStreamMode> enumeration that describes the type of access permitted to the **CryptoStream**.</span></span> <span data-ttu-id="1dafb-109">**CryptoStream** クラスは、 <xref:System.IO.Stream> クラスから派生する任意のクラス ( <xref:System.IO.FileStream>、 <xref:System.IO.MemoryStream>、 <xref:System.Net.Sockets.NetworkStream>など) を使用して初期化できます。</span><span class="sxs-lookup"><span data-stu-id="1dafb-109">The **CryptoStream** class can be initialized using any class that derives from the <xref:System.IO.Stream> class, including <xref:System.IO.FileStream>, <xref:System.IO.MemoryStream>, and <xref:System.Net.Sockets.NetworkStream>.</span></span> <span data-ttu-id="1dafb-110">これらのクラスを使用すると、さまざまなストリーム オブジェクトの対称暗号化を実行できます。</span><span class="sxs-lookup"><span data-stu-id="1dafb-110">Using these classes, you can perform symmetric encryption on a variety of stream objects.</span></span>  
  
 <span data-ttu-id="1dafb-111">次の例は、Rijndael 暗号化アルゴリズムを実装する <xref:System.Security.Cryptography.RijndaelManaged> クラスの新しいインスタンスを作成し、これを使用して **CryptoStream** クラスで暗号化を実行する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="1dafb-111">The following example illustrates how to create a new instance of the <xref:System.Security.Cryptography.RijndaelManaged> class, which implements the Rijndael encryption algorithm, and use it to perform encryption on a **CryptoStream** class.</span></span> <span data-ttu-id="1dafb-112">この例では、 **CryptoStream** は `myStream` と呼ばれるストリーム オブジェクトで初期化されています。これは任意の種類のマネージド ストリームにすることができます。</span><span class="sxs-lookup"><span data-stu-id="1dafb-112">In this example, the **CryptoStream** is initialized with a stream object called `myStream` that can be any type of managed stream.</span></span> <span data-ttu-id="1dafb-113">**RijndaelManaged** クラスの **CreateEncryptor** メソッドには、暗号化で使用されるキーと IV が渡されます。</span><span class="sxs-lookup"><span data-stu-id="1dafb-113">The **CreateEncryptor** method from the **RijndaelManaged** class is passed the key and IV that are used for encryption.</span></span> <span data-ttu-id="1dafb-114">この場合、 `rmCrypto` から生成された既定のキーと IV が使用されます。</span><span class="sxs-lookup"><span data-stu-id="1dafb-114">In this case, the default key and IV generated from `rmCrypto` are used.</span></span> <span data-ttu-id="1dafb-115">最後に、ストリームへの書き込みのアクセスを指定する **CryptoStreamMode.Write** が渡されます。</span><span class="sxs-lookup"><span data-stu-id="1dafb-115">Finally, the **CryptoStreamMode.Write** is passed, specifying write access to the stream.</span></span>  
  
```vb  
Dim rmCrypto As New RijndaelManaged()  
Dim cryptStream As New CryptoStream(myStream, rmCrypto.CreateEncryptor(rmCrypto.Key, rmCrypto.IV), CryptoStreamMode.Write)  
```  
  
```csharp  
RijndaelManaged rmCrypto = new RijndaelManaged();  
CryptoStream cryptStream = new CryptoStream(myStream, rmCrypto.CreateEncryptor(), CryptoStreamMode.Write);  
```  
  
 <span data-ttu-id="1dafb-116">このコードの実行後に **CryptoStream** オブジェクトに書き込まれたデータはすべて、Rijndael アルゴリズムを使用して暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="1dafb-116">After this code is executed, any data written to the **CryptoStream** object is encrypted using the Rijndael algorithm.</span></span>  
  
 <span data-ttu-id="1dafb-117">次の例は、ストリームの作成、ストリームの暗号化、ストリームへの書き込み、およびストリームを閉じるプロセス全体を示しています。</span><span class="sxs-lookup"><span data-stu-id="1dafb-117">The following example shows the entire process of creating a stream, encrypting the stream, writing to the stream, and closing the stream.</span></span> <span data-ttu-id="1dafb-118">この例では、 **CryptoStream** クラスと **RijndaelManaged** クラスを使用して暗号化されたネットワーク ストリームを作成します。</span><span class="sxs-lookup"><span data-stu-id="1dafb-118">This example creates a network stream that is encrypted using the **CryptoStream** class and the **RijndaelManaged** class.</span></span> <span data-ttu-id="1dafb-119"><xref:System.IO.StreamWriter> クラスを使用して、暗号化されたストリームにメッセージが書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="1dafb-119">A message is written to the encrypted stream with the <xref:System.IO.StreamWriter> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1dafb-120">また、この例を使用してファイルに書き込むこともできます。</span><span class="sxs-lookup"><span data-stu-id="1dafb-120">You can also use this example to write to a file.</span></span> <span data-ttu-id="1dafb-121">それを行うには、 <xref:System.Net.Sockets.TcpClient> の参照を削除し、 <xref:System.Net.Sockets.NetworkStream> を <xref:System.IO.FileStream>に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="1dafb-121">To do that, delete the <xref:System.Net.Sockets.TcpClient> reference and replace the <xref:System.Net.Sockets.NetworkStream> with a <xref:System.IO.FileStream>.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Security.Cryptography  
Imports System.Net.Sockets  
  
Module Module1  
Sub Main()  
   Try  
      'Create a TCP connection to a listening TCP process.  
      'Use "localhost" to specify the current computer or  
      'replace "localhost" with the IP address of the   
      'listening process.   
      Dim tcp As New TcpClient("localhost", 11000)  
  
      'Create a network stream from the TCP connection.   
      Dim netStream As NetworkStream = tcp.GetStream()  
  
      'Create a new instance of the RijndaelManaged class  
      'and encrypt the stream.  
      Dim rmCrypto As New RijndaelManaged()  
  
            Dim key As Byte() = {&H1, &H2, &H3, &H4, &H5, &H6, &H7, &H8, &H9, &H10, &H11, &H12, &H13, &H14, &H15, &H16}  
            Dim iv As Byte() = {&H1, &H2, &H3, &H4, &H5, &H6, &H7, &H8, &H9, &H10, &H11, &H12, &H13, &H14, &H15, &H16}  
  
      'Create a CryptoStream, pass it the NetworkStream, and encrypt   
      'it with the Rijndael class.  
      Dim cryptStream As New CryptoStream(netStream, rmCrypto.CreateEncryptor(key, iv), CryptoStreamMode.Write)  
  
      'Create a StreamWriter for easy writing to the   
      'network stream.  
      Dim sWriter As New StreamWriter(cryptStream)  
  
      'Write to the stream.  
      sWriter.WriteLine("Hello World!")  
  
      'Inform the user that the message was written  
      'to the stream.  
      Console.WriteLine("The message was sent.")  
  
      'Close all the connections.  
      sWriter.Close()  
      cryptStream.Close()  
      netStream.Close()  
      tcp.Close()  
   Catch  
      'Inform the user that an exception was raised.  
      Console.WriteLine("The connection failed.")  
   End Try  
End Sub  
End Module  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Security.Cryptography;  
using System.Net.Sockets;  
  
public class main  
{  
   public static void Main(string[] args)  
   {  
      try  
      {  
         //Create a TCP connection to a listening TCP process.  
         //Use "localhost" to specify the current computer or  
         //replace "localhost" with the IP address of the   
         //listening process.    
         TcpClient tcp = new TcpClient("localhost",11000);  
  
         //Create a network stream from the TCP connection.   
         NetworkStream netStream = tcp.GetStream();  
  
         //Create a new instance of the RijndaelManaged class  
         // and encrypt the stream.  
         RijndaelManaged rmCrypto = new RijndaelManaged();  
  
         byte[] key = {0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x10, 0x11, 0x12, 0x13, 0x14, 0x15, 0x16};  
         byte[] iv = {0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x10, 0x11, 0x12, 0x13, 0x14, 0x15, 0x16};  
  
         //Create a CryptoStream, pass it the NetworkStream, and encrypt   
         //it with the Rijndael class.  
         CryptoStream cryptStream = new CryptoStream(netStream,   
         rmCrypto.CreateEncryptor(key, iv),     
         CryptoStreamMode.Write);  
  
         //Create a StreamWriter for easy writing to the   
         //network stream.  
         StreamWriter sWriter = new StreamWriter(cryptStream);  
  
         //Write to the stream.  
         sWriter.WriteLine("Hello World!");  
  
         //Inform the user that the message was written  
         //to the stream.  
         Console.WriteLine("The message was sent.");  
  
         //Close all the connections.  
         sWriter.Close();  
         cryptStream.Close();  
         netStream.Close();  
         tcp.Close();  
      }  
      catch  
      {  
         //Inform the user that an exception was raised.  
         Console.WriteLine("The connection failed.");  
      }  
   }  
}  
```  
  
 <span data-ttu-id="1dafb-122">前の例を正しく実行するためには、 <xref:System.Net.Sockets.TcpClient> クラスで指定された IP アドレスとポート番号をリッスンしているプロセスが存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1dafb-122">For the previous example to execute successfully, there must be a process listening on the IP address and port number specified in the <xref:System.Net.Sockets.TcpClient> class.</span></span> <span data-ttu-id="1dafb-123">リッスンしているプロセスが存在する場合は、コードがリッスンしているプロセスに接続して、Rijndael の対称アルゴリズムを使用してストリームを暗号化し、"Hello World!" を</span><span class="sxs-lookup"><span data-stu-id="1dafb-123">If a listening process exists, the code will connect to the listening process, encrypt the stream using the Rijndael symmetric algorithm, and write "Hello World!"</span></span> <span data-ttu-id="1dafb-124">ストリームに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="1dafb-124">to the stream.</span></span> <span data-ttu-id="1dafb-125">コードが正常に実行された場合、コンソールに次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1dafb-125">If the code is successful, it displays the following text to the console:</span></span>  
  
```console  
The message was sent.  
```  
  
 <span data-ttu-id="1dafb-126">ただし、リッスンしているプロセスが見つからないか、例外が発生した場合、コードによってコンソールに次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1dafb-126">However, if no listening process is found or an exception is raised, the code displays the following text to the console:</span></span>  
  
```console  
The connection failed.  
```  
  
## <a name="asymmetric-encryption"></a><span data-ttu-id="1dafb-127">非対称暗号化</span><span class="sxs-lookup"><span data-stu-id="1dafb-127">Asymmetric Encryption</span></span>  
 <span data-ttu-id="1dafb-128">非対称アルゴリズムは、通常は対称キーと IV の暗号化など、少量のデータの暗号化に使用されます。</span><span class="sxs-lookup"><span data-stu-id="1dafb-128">Asymmetric algorithms are usually used to encrypt small amounts of data such as the encryption of a symmetric key and IV.</span></span> <span data-ttu-id="1dafb-129">通常、非対称暗号化を行う個人や組織は、別のパーティによって生成された公開キーを使用します。</span><span class="sxs-lookup"><span data-stu-id="1dafb-129">Typically, an individual performing asymmetric encryption uses the public key generated by another party.</span></span> <span data-ttu-id="1dafb-130"><xref:System.Security.Cryptography.RSACryptoServiceProvider> クラスは、この目的のために、.NET Framework によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="1dafb-130">The <xref:System.Security.Cryptography.RSACryptoServiceProvider> class is provided by the .NET Framework for this purpose.</span></span>  
  
 <span data-ttu-id="1dafb-131">次の例では、公開キーの情報を使用して対称キーと IV を暗号化します。</span><span class="sxs-lookup"><span data-stu-id="1dafb-131">The following example uses public key information to encrypt a symmetric key and IV.</span></span> <span data-ttu-id="1dafb-132">サード パーティの公開キーを表す 2 つのバイト配列が初期化されます。</span><span class="sxs-lookup"><span data-stu-id="1dafb-132">Two byte arrays are initialized that represent the public key of a third party.</span></span> <span data-ttu-id="1dafb-133"><xref:System.Security.Cryptography.RSAParameters> オブジェクトがこれらの値に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="1dafb-133">An <xref:System.Security.Cryptography.RSAParameters> object is initialized to these values.</span></span> <span data-ttu-id="1dafb-134">次に、 **RSAParameters** オブジェクトが (このオブジェクトが表す公開キーと共に) **メソッドを使用して** RSACryptoServiceProvider <xref:System.Security.Cryptography.RSACryptoServiceProvider.ImportParameters%2A?displayProperty=nameWithType> にインポートされます。</span><span class="sxs-lookup"><span data-stu-id="1dafb-134">Next, the **RSAParameters** object (along with the public key it represents) is imported into an **RSACryptoServiceProvider** using the <xref:System.Security.Cryptography.RSACryptoServiceProvider.ImportParameters%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="1dafb-135">最後に、 <xref:System.Security.Cryptography.RijndaelManaged> クラスが作成した秘密キーと IV が暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="1dafb-135">Finally, the private key and IV created by a <xref:System.Security.Cryptography.RijndaelManaged> class are encrypted.</span></span> <span data-ttu-id="1dafb-136">この例では、システムに 128 ビット暗号化がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1dafb-136">This example requires systems to have 128-bit encryption installed.</span></span>  
  
```vb  
Imports System  
Imports System.Security.Cryptography  
  
Module Module1  
  
    Sub Main()  
        'Initialize the byte arrays to the public key information.  
      Dim publicKey As Byte() =  {214, 46, 220, 83, 160, 73, 40, 39, 201, 155, 19,202, 3, 11, 191, 178, 56, 74, 90, 36, 248, 103, 18, 144, 170, 163, 145, 87, 54, 61, 34, 220, 222, 207, 137, 149, 173, 14, 92, 120, 206, 222, 158, 28, 40, 24, 30, 16, 175, 108, 128, 35, 230, 118, 40, 121, 113, 125, 216, 130, 11, 24, 90, 48, 194, 240, 105, 44, 76, 34, 57, 249, 228, 125, 80, 38, 9, 136, 29, 117, 207, 139, 168, 181, 85, 137, 126, 10, 126, 242, 120, 247, 121, 8, 100, 12, 201, 171, 38, 226, 193, 180, 190, 117, 177, 87, 143, 242, 213, 11, 44, 180, 113, 93, 106, 99, 179, 68, 175, 211, 164, 116, 64, 148, 226, 254, 172, 147}  
  
        Dim exponent As Byte() = {1, 0, 1}  
  
        'Create values to store encrypted symmetric keys.  
        Dim encryptedSymmetricKey() As Byte  
        Dim encryptedSymmetricIV() As Byte  
  
        'Create a new instance of the RSACryptoServiceProvider class.  
        Dim rsa As New RSACryptoServiceProvider()  
  
        'Create a new instance of the RSAParameters structure.  
        Dim rsaKeyInfo As New RSAParameters()  
  
        'Set rsaKeyInfo to the public key values.   
        rsaKeyInfo.Modulus = publicKey  
        rsaKeyInfo.Exponent = exponent  
  
        'Import key parameters into rsa.  
        rsa.ImportParameters(rsaKeyInfo)  
  
        'Create a new instance of the RijndaelManaged class.  
        Dim RM As New RijndaelManaged()  
  
        'Encrypt the symmetric key and IV.  
        encryptedSymmetricKey = rsa.Encrypt(RM.Key, False)  
        encryptedSymmetricIV = rsa.Encrypt(RM.IV, False)  
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
      byte[] publicKey = {214,46,220,83,160,73,40,39,201,155,19,202,3,11,191,178,56,  
            74,90,36,248,103,18,144,170,163,145,87,54,61,34,220,222,  
            207,137,149,173,14,92,120,206,222,158,28,40,24,30,16,175,  
            108,128,35,230,118,40,121,113,125,216,130,11,24,90,48,194,  
            240,105,44,76,34,57,249,228,125,80,38,9,136,29,117,207,139,  
            168,181,85,137,126,10,126,242,120,247,121,8,100,12,201,171,  
            38,226,193,180,190,117,177,87,143,242,213,11,44,180,113,93,  
            106,99,179,68,175,211,164,116,64,148,226,254,172,147};  
  
      byte[] exponent = {1,0,1};  
  
      //Create values to store encrypted symmetric keys.  
      byte[] encryptedSymmetricKey;  
      byte[] encryptedSymmetricIV;  
  
      //Create a new instance of the RSACryptoServiceProvider class.  
      RSACryptoServiceProvider rsa = new RSACryptoServiceProvider();  
  
      //Create a new instance of the RSAParameters structure.  
      RSAParameters rsaKeyInfo = new RSAParameters();  
  
      //Set rsaKeyInfo to the public key values.   
      rsaKeyInfo.Modulus = publicKey;  
      rsaKeyInfo.Exponent = exponent;  
  
      //Import key parameters into RSA.  
      rsa.ImportParameters(rsaKeyInfo);  
  
      //Create a new instance of the RijndaelManaged class.  
      RijndaelManaged rm = new RijndaelManaged();  
  
      //Encrypt the symmetric key and IV.  
      encryptedSymmetricKey = rsa.Encrypt(rm.Key, false);  
      encryptedSymmetricIV = rsa.Encrypt(rm.IV, false);  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="1dafb-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="1dafb-137">See also</span></span>

- [<span data-ttu-id="1dafb-138">暗号化と復号化のためのキーの生成</span><span class="sxs-lookup"><span data-stu-id="1dafb-138">Generating Keys for Encryption and Decryption</span></span>](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md)
- [<span data-ttu-id="1dafb-139">データの復号化</span><span class="sxs-lookup"><span data-stu-id="1dafb-139">Decrypting Data</span></span>](../../../docs/standard/security/decrypting-data.md)
- [<span data-ttu-id="1dafb-140">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="1dafb-140">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
