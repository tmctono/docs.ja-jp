---
title: レジストリにキーを作成する方法 - C# プログラミング ガイド
description: レジストリにキーを作成する方法について説明します。 コード例、コンパイル手順、および使用可能なその他のリソースを参照してください。
ms.date: 07/20/2015
helpviewer_keywords:
- registry, adding keys and values [C#]
- registry keys, creating [C#]
- keys, creating in registry
ms.assetid: 8fa475b0-e01f-483a-9327-fd03488fdf5d
ms.openlocfilehash: c51fa61aa4c501921d5c7ace99a8c5aaf7b29f58
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203918"
---
# <a name="how-to-create-a-key-in-the-registry-c-programming-guide"></a><span data-ttu-id="0e46d-104">レジストリにキーを作成する方法 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="0e46d-104">How to create a key in the registry (C# Programming Guide)</span></span>

<span data-ttu-id="0e46d-105">現在のユーザーのレジストリに存在する "Names" というキーの下に "Name" と "Isabella" という値のペアを追加する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0e46d-105">This example adds the value pair, "Name" and "Isabella", to the current user's registry, under the key "Names".</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e46d-106">例</span><span class="sxs-lookup"><span data-stu-id="0e46d-106">Example</span></span>  
  
```csharp  
Microsoft.Win32.RegistryKey key;  
key = Microsoft.Win32.Registry.CurrentUser.CreateSubKey("Names");  
key.SetValue("Name", "Isabella");  
key.Close();  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0e46d-107">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="0e46d-107">Compiling the Code</span></span>  
  
- <span data-ttu-id="0e46d-108">コードをコピーし、コンソール アプリケーションの `Main` メソッドに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="0e46d-108">Copy the code and paste it into the `Main` method of a console application.</span></span>  
  
- <span data-ttu-id="0e46d-109">`Names` パラメーターをレジストリの HKEY_CURRENT_USER ノードの直下にあるキーの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="0e46d-109">Replace the `Names` parameter with the name of a key that exists directly under the HKEY_CURRENT_USER node of the registry.</span></span>  
  
- <span data-ttu-id="0e46d-110">`Name` パラメーターを Names ノードの直下にある値の名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="0e46d-110">Replace the `Name` parameter with the name of a value that exists directly under the Names node.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="0e46d-111">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="0e46d-111">Robust Programming</span></span>  

 <span data-ttu-id="0e46d-112">レジストリの構造を調べて、キーの適切な場所を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="0e46d-112">Examine the registry structure to find a suitable location for your key.</span></span> <span data-ttu-id="0e46d-113">たとえば、現在のユーザーの Software キーを開き、会社名のキーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0e46d-113">For example, you might want to open the Software key of the current user, and create a key with your company's name.</span></span> <span data-ttu-id="0e46d-114">その後で、会社名のキーにレジストリ値を追加します。</span><span class="sxs-lookup"><span data-stu-id="0e46d-114">Then add the registry values to your company's key.</span></span>  
  
 <span data-ttu-id="0e46d-115">次の条件では例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0e46d-115">The following conditions might cause an exception:</span></span>  
  
- <span data-ttu-id="0e46d-116">キーの名前が null である場合。</span><span class="sxs-lookup"><span data-stu-id="0e46d-116">The name of the key is null.</span></span>  
  
- <span data-ttu-id="0e46d-117">レジストリ キーを作成するためのアクセス許可がユーザーにない場合。</span><span class="sxs-lookup"><span data-stu-id="0e46d-117">The user does not have permissions to create registry keys.</span></span>  
  
- <span data-ttu-id="0e46d-118">キー名が 255 文字の制限を超えている場合。</span><span class="sxs-lookup"><span data-stu-id="0e46d-118">The key name exceeds the 255-character limit.</span></span>  
  
- <span data-ttu-id="0e46d-119">キーが閉じている場合。</span><span class="sxs-lookup"><span data-stu-id="0e46d-119">The key is closed.</span></span>  
  
- <span data-ttu-id="0e46d-120">レジストリ キーが読み取り専用の場合。</span><span class="sxs-lookup"><span data-stu-id="0e46d-120">The registry key is read-only.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="0e46d-121">.NET セキュリティ</span><span class="sxs-lookup"><span data-stu-id="0e46d-121">.NET Security</span></span>  

 <span data-ttu-id="0e46d-122">ローカル コンピューター (`Microsoft.Win32.Registry.CurrentUser`) よりもユーザー フォルダー (`Microsoft.Win32.Registry.LocalMachine`) にデータを書き込む方が安全です。</span><span class="sxs-lookup"><span data-stu-id="0e46d-122">It is more secure to write data to the user folder — `Microsoft.Win32.Registry.CurrentUser` — rather than to the local computer — `Microsoft.Win32.Registry.LocalMachine`.</span></span>  
  
 <span data-ttu-id="0e46d-123">レジストリの値を作成するときは、その値が既存の値である場合の処理を決めておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e46d-123">When you create a registry value, you need to decide what to do if that value already exists.</span></span> <span data-ttu-id="0e46d-124">悪意のあるユーザーによって作成された別のプロセスが既に値を作成し、アクセス権を持っている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0e46d-124">Another process, perhaps a malicious one, may have already created the value and have access to it.</span></span> <span data-ttu-id="0e46d-125">レジストリ値にデータを設定すると、そのデータを他のプロセスから利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="0e46d-125">When you put data in the registry value, the data is available to the other process.</span></span> <span data-ttu-id="0e46d-126">これを回避するには、`Overload:Microsoft.Win32.RegistryKey.GetValue`</span><span class="sxs-lookup"><span data-stu-id="0e46d-126">To prevent this, use the.`Overload:Microsoft.Win32.RegistryKey.GetValue`</span></span> <span data-ttu-id="0e46d-127">メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="0e46d-127">method.</span></span> <span data-ttu-id="0e46d-128">このメソッドは、キーがまだ存在しない場合、null を返します。</span><span class="sxs-lookup"><span data-stu-id="0e46d-128">It returns null if the key does not already exist.</span></span>  
  
 <span data-ttu-id="0e46d-129">レジストリ キーがアクセス制御リスト (ACL: Access Control List) によって保護されていても、パスワードなど他人に知られたくないデータをプレーン テキストでレジストリに格納するのは危険です。</span><span class="sxs-lookup"><span data-stu-id="0e46d-129">It is not secure to store secrets, such as passwords, in the registry as plain text, even if the registry key is protected by access control lists (ACL).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e46d-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="0e46d-130">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="0e46d-131">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="0e46d-131">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="0e46d-132">ファイル システムとレジストリ (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="0e46d-132">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
- [<span data-ttu-id="0e46d-133">C# によるレジストリからの読み取り、書き込み、および削除</span><span class="sxs-lookup"><span data-stu-id="0e46d-133">Read, write and delete from the registry with C#</span></span>](https://www.codeproject.com/Articles/3389/Read-write-and-delete-from-registry-with-C)
