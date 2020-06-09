---
title: '方法: データ保護の使用'
description: .NET でデータ保護 API (DPAPI) にアクセスしてデータ保護を使用する方法について説明します。
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DPAPI
- encryption [.NET Framework], data protection API
- data [.NET Framework], decryption
- ProtectedMemory class, about ProtectedMemory class
- ProtectedData class, about ProtectedData class
- cryptography [.NET Framework], data protection API
- data protection API [.NET Framework]
- decryption
- data [.NET Framework], encryption
ms.assetid: 606698b0-cb1a-42ca-beeb-0bea34205d20
ms.openlocfilehash: c7f88105727dfd33c87a815054aa317ac2052e83
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598594"
---
# <a name="how-to-use-data-protection"></a><span data-ttu-id="a1db6-103">方法: データ保護の使用</span><span class="sxs-lookup"><span data-stu-id="a1db6-103">How to: Use Data Protection</span></span>
<span data-ttu-id="a1db6-104">.NET Framework では、データ保護 API (DPAPI) へのアクセスを提供しています。DPAPI を使用すると、現在のユーザー アカウントまたはコンピューターからの情報を使用してデータを暗号化できます。</span><span class="sxs-lookup"><span data-stu-id="a1db6-104">The .NET Framework provides access to the data protection API (DPAPI), which allows you to encrypt data using information from the current user account or computer.</span></span>  <span data-ttu-id="a1db6-105">DPAPI を使用すると、暗号化キーを明示的に生成および格納するという困難な問題を軽減できます。</span><span class="sxs-lookup"><span data-stu-id="a1db6-105">When you use the DPAPI, you alleviate the difficult problem of explicitly generating and storing a cryptographic key.</span></span>  
  
 <span data-ttu-id="a1db6-106"><xref:System.Security.Cryptography.ProtectedMemory> クラスを使用すると、メモリ内のバイト配列を暗号化できます。</span><span class="sxs-lookup"><span data-stu-id="a1db6-106">Use the <xref:System.Security.Cryptography.ProtectedMemory> class to encrypt an array of in-memory bytes.</span></span>  <span data-ttu-id="a1db6-107">この機能は、Microsoft Windows XP 以降のオペレーティング システムで使用できます。</span><span class="sxs-lookup"><span data-stu-id="a1db6-107">This functionality is available in Microsoft Windows XP and later operating systems.</span></span>  <span data-ttu-id="a1db6-108">現在のプロセスによって暗号化されるメモリは、現在のプロセスのみ、すべてのプロセス、または同じユーザーのコンテキストによって復号化されることを指定できます。</span><span class="sxs-lookup"><span data-stu-id="a1db6-108">You can specify that memory encrypted by the current process can be decrypted by the current process only, by all processes, or from the same user context.</span></span>  <span data-ttu-id="a1db6-109"><xref:System.Security.Cryptography.ProtectedMemory> オプションの詳しい説明については、「<xref:System.Security.Cryptography.MemoryProtectionScope> 列挙型」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1db6-109">See the <xref:System.Security.Cryptography.MemoryProtectionScope> enumeration for a detailed description of <xref:System.Security.Cryptography.ProtectedMemory> options.</span></span>  
  
 <span data-ttu-id="a1db6-110">バイト配列のコピーを暗号化するには、<xref:System.Security.Cryptography.ProtectedData> クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="a1db6-110">Use the <xref:System.Security.Cryptography.ProtectedData> class to encrypt a copy of an array of bytes.</span></span> <span data-ttu-id="a1db6-111">この機能は、Microsoft Windows 2000 以降のオペレーティング システムで使用できます。</span><span class="sxs-lookup"><span data-stu-id="a1db6-111">This functionality is available in Microsoft Windows 2000 and later operating systems.</span></span>  <span data-ttu-id="a1db6-112">現在のユーザー アカウントによって暗号化されたデータは、同じユーザー アカウントによってのみ復号化できることを指定できます。あるいは、現在のユーザー アカウントによって暗号化されたデータは、コンピューター上の任意のアカウントによって復号化できることを指定できます。</span><span class="sxs-lookup"><span data-stu-id="a1db6-112">You can specify that data encrypted by the current user account can be decrypted only by the same user account, or you can specify that data encrypted by the current user account can be decrypted by any account on the computer.</span></span>  <span data-ttu-id="a1db6-113"><xref:System.Security.Cryptography.ProtectedData> オプションの詳しい説明については、「<xref:System.Security.Cryptography.DataProtectionScope> 列挙型」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1db6-113">See the <xref:System.Security.Cryptography.DataProtectionScope> enumeration for a detailed description of <xref:System.Security.Cryptography.ProtectedData> options.</span></span>  
  
### <a name="to-encrypt-in-memory-data-using-data-protection"></a><span data-ttu-id="a1db6-114">データの保護を使用してメモリ内のデータを暗号化するには</span><span class="sxs-lookup"><span data-stu-id="a1db6-114">To encrypt in-memory data using data protection</span></span>  
  
1. <span data-ttu-id="a1db6-115">暗号化するバイト配列、エントロピ、およびメモリ保護スコープを渡す際に、静的な <xref:System.Security.Cryptography.ProtectedMemory.Protect%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a1db6-115">Call the static <xref:System.Security.Cryptography.ProtectedMemory.Protect%2A> method while passing an array of bytes to encrypt, the entropy, and the memory protection scope.</span></span>  
  
### <a name="to-decrypt-in-memory-data-using-data-protection"></a><span data-ttu-id="a1db6-116">データ保護を使用してメモリ内のデータを復号化するには</span><span class="sxs-lookup"><span data-stu-id="a1db6-116">To decrypt in-memory data using data protection</span></span>  
  
1. <span data-ttu-id="a1db6-117">復号化するバイト配列およびメモリ保護スコープを渡す際に、静的な <xref:System.Security.Cryptography.ProtectedMemory.Unprotect%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a1db6-117">Call the static <xref:System.Security.Cryptography.ProtectedMemory.Unprotect%2A> method while passing an array of bytes to decrypt and the memory protection scope.</span></span>  
  
### <a name="to-encrypt-data-to-a-file-or-stream-using-data-protection"></a><span data-ttu-id="a1db6-118">データ保護を使用してファイルやストリームのデータを暗号化するには</span><span class="sxs-lookup"><span data-stu-id="a1db6-118">To encrypt data to a file or stream using data protection</span></span>  
  
1. <span data-ttu-id="a1db6-119">ランダム エントロピを作成します。</span><span class="sxs-lookup"><span data-stu-id="a1db6-119">Create random entropy.</span></span>  
  
2. <span data-ttu-id="a1db6-120">暗号化するバイト配列、エントロピ、およびデータ保護スコープを渡す際に、静的な <xref:System.Security.Cryptography.ProtectedData.Protect%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a1db6-120">Call the static <xref:System.Security.Cryptography.ProtectedData.Protect%2A> method while passing an array of bytes to encrypt, the entropy, and the data protection scope.</span></span>  
  
3. <span data-ttu-id="a1db6-121">ファイルまたはストリームに暗号化されたデータを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="a1db6-121">Write the encrypted data to a file or stream.</span></span>  
  
### <a name="to-decrypt-data-from-a-file-or-stream-using-data-protection"></a><span data-ttu-id="a1db6-122">データ保護を使用してファイルやストリームからデータを復号化するには</span><span class="sxs-lookup"><span data-stu-id="a1db6-122">To decrypt data from a file or stream using data protection</span></span>  
  
1. <span data-ttu-id="a1db6-123">ファイルまたはストリームから暗号化されたデータを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="a1db6-123">Read the encrypted data from a file or stream.</span></span>  
  
2. <span data-ttu-id="a1db6-124">復号化するバイト配列およびデータ保護スコープを渡す際に、静的な <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a1db6-124">Call the static <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A> method while passing an array of bytes to decrypt and the data protection scope.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1db6-125">例</span><span class="sxs-lookup"><span data-stu-id="a1db6-125">Example</span></span>  
 <span data-ttu-id="a1db6-126">次のコード例は、暗号化と復号化の 2 つの形式を示しています。</span><span class="sxs-lookup"><span data-stu-id="a1db6-126">The following code example demonstrates two forms of encryption and decryption.</span></span>  <span data-ttu-id="a1db6-127">最初に、コード例では、メモリ内のバイト配列を暗号化してから復号化します。</span><span class="sxs-lookup"><span data-stu-id="a1db6-127">First, the code example encrypts and then decrypts an in-memory array of bytes.</span></span>  <span data-ttu-id="a1db6-128">次に、コード例では、バイト配列のコピーを暗号化し、ファイルに保存して、そのファイルからデータを読み込み、その後データを復号化しています。</span><span class="sxs-lookup"><span data-stu-id="a1db6-128">Next, the code example encrypts a copy of a byte array, saves it to a file, loads the data back from the file, and then decrypts the data.</span></span>  <span data-ttu-id="a1db6-129">例では、元のデータ、暗号化されたデータ、および復号化されたデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a1db6-129">The example displays the original data, the encrypted data, and the decrypted data.</span></span>  
  
 [!code-csharp[DPAPI-HowTO#1](../../../samples/snippets/csharp/VS_Snippets_CLR/DPAPI-HowTO/cs/sample.cs#1)]
 [!code-vb[DPAPI-HowTO#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DPAPI-HowTO/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a1db6-130">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="a1db6-130">Compiling the Code</span></span>  
  
- <span data-ttu-id="a1db6-131">`System.Security.dll` への参照を含めます。</span><span class="sxs-lookup"><span data-stu-id="a1db6-131">Include a reference to `System.Security.dll`.</span></span>  
  
- <span data-ttu-id="a1db6-132"><xref:System>、<xref:System.IO>、<xref:System.Security.Cryptography>、および <xref:System.Text> 名前空間を含めます。</span><span class="sxs-lookup"><span data-stu-id="a1db6-132">Include the <xref:System>, <xref:System.IO>, <xref:System.Security.Cryptography>, and <xref:System.Text> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1db6-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1db6-133">See also</span></span>

- <xref:System.Security.Cryptography.ProtectedMemory>
- <xref:System.Security.Cryptography.ProtectedData>
