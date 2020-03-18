---
title: '方法 : レジストリ キーから値を読み取る'
ms.date: 07/20/2015
helpviewer_keywords:
- registry keys [Visual Basic], determining if a value exists in
- My.Computer.Registry object, examples
- registry [Visual Basic], determining if values exist
- registry keys [Visual Basic], reading from
- registry [Visual Basic], reading
ms.assetid: 775d0a57-68c9-464e-8949-9a39bd29cc64
ms.openlocfilehash: 73c32aefe06a68bb42fcb5f4615da0927e57e892
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "74345617"
---
# <a name="how-to-read-a-value-from-a-registry-key-in-visual-basic"></a><span data-ttu-id="a751b-102">方法 : Visual Basic で、レジストリ キーから値を読み取る</span><span class="sxs-lookup"><span data-stu-id="a751b-102">How to: Read a Value from a Registry Key in Visual Basic</span></span>

<span data-ttu-id="a751b-103">`GetValue` オブジェクトの `My.Computer.Registry` メソッドは、Windows レジストリ内の値を読み込むために使用できます。</span><span class="sxs-lookup"><span data-stu-id="a751b-103">The `GetValue` method of the `My.Computer.Registry` object can be used to read values in the Windows registry.</span></span>  
  
 <span data-ttu-id="a751b-104">キー (次の例では "Software\MyApp") が存在しない場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="a751b-104">If the key, "Software\MyApp" in the following example, does not exist, an exception is thrown.</span></span> <span data-ttu-id="a751b-105">`ValueName` (次の例では "Name") が存在しない場合は、`Nothing` が返されます。</span><span class="sxs-lookup"><span data-stu-id="a751b-105">If the `ValueName`,  "Name" in the following example, does not exist, `Nothing` is returned.</span></span>  
  
 <span data-ttu-id="a751b-106">`GetValue` メソッドは、特定のレジストリ キー内に値が存在するかどうかを確認するためにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="a751b-106">The `GetValue` method can also be used to determine whether a given value exists in a specific registry key.</span></span>  
  
 <span data-ttu-id="a751b-107">コードが Web アプリケーションからレジストリを読み取る際、現在のユーザーは Web アプリケーションに実装されている認証と偽装によって決定されます。</span><span class="sxs-lookup"><span data-stu-id="a751b-107">When code reads the registry from a Web application, the current user is determined by the authentication and impersonation that is implemented in the Web application.</span></span>  
  
### <a name="to-read-a-value-from-a-registry-key"></a><span data-ttu-id="a751b-108">レジストリ キーから値を読み取るには</span><span class="sxs-lookup"><span data-stu-id="a751b-108">To read a value from a registry key</span></span>  
  
- <span data-ttu-id="a751b-109">`GetValue` メソッドを使用してパスと名前を指定し、レジストリ キーから値を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="a751b-109">Use the `GetValue` method, specifying the path and name) to read a value from registry key.</span></span> <span data-ttu-id="a751b-110">次の例は、`Name` から値 `HKEY_CURRENT_USER\Software\MyApp` を読み取り、その値をメッセージ ボックスに表示します。</span><span class="sxs-lookup"><span data-stu-id="a751b-110">The following example reads the value `Name` from `HKEY_CURRENT_USER\Software\MyApp` and displays it in a message box.</span></span>  
  
     [!code-vb[VbResourceTasks#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#4)]  
  
 <span data-ttu-id="a751b-111">このコード例は IntelliSense コード スニペットとしても利用できます。</span><span class="sxs-lookup"><span data-stu-id="a751b-111">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="a751b-112">コード スニペット ピッカーでは、これは **[Windows オペレーティング システム] > [レジストリ]** に配置されます。</span><span class="sxs-lookup"><span data-stu-id="a751b-112">In the code snippet picker, it is located in **Windows Operating System > Registry**.</span></span> <span data-ttu-id="a751b-113">詳細については、「 [Code Snippets](/visualstudio/ide/code-snippets)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a751b-113">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
### <a name="to-determine-whether-a-value-exists-in-a-registry-key"></a><span data-ttu-id="a751b-114">レジストリ キー内値が存在するかどうかを確認するには</span><span class="sxs-lookup"><span data-stu-id="a751b-114">To determine whether a value exists in a registry key</span></span>  
  
- <span data-ttu-id="a751b-115">`GetValue` メソッドを使用して値を取得します。</span><span class="sxs-lookup"><span data-stu-id="a751b-115">Use the `GetValue` method to retrieve the value.</span></span> <span data-ttu-id="a751b-116">次のコードは、値が存在するかどうかを確認し、存在しない場合にはメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="a751b-116">The following code checks whether the value exists and returns a message if it does not.</span></span>  
  
     [!code-vb[VbResourceTasks#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#12)]  
  
## <a name="robust-programming"></a><span data-ttu-id="a751b-117">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="a751b-117">Robust Programming</span></span>  

 <span data-ttu-id="a751b-118">レジストリは、データの格納に使用される最上位レベル (またはルート) のキーを保持します。</span><span class="sxs-lookup"><span data-stu-id="a751b-118">The registry holds top-level, or root, keys that are used to store data.</span></span> <span data-ttu-id="a751b-119">たとえば、HKEY_LOCAL_MACHINE ルート キーは、すべてのユーザーによって使用される、マシン レベルの設定を格納するため使用されます。これに対し HKEY_CURRENT_USER は、個々のユーザーに固有のデータを格納するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a751b-119">For instance, the HKEY_LOCAL_MACHINE root key is used for storing machine-level settings used by all users, while HKEY_CURRENT_USER is used for storing data specific to an individual user.</span></span>  
  
 <span data-ttu-id="a751b-120">次の条件を満たす場合は、例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a751b-120">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="a751b-121">キーの名前が `Nothing` である場合 (<xref:System.ArgumentNullException>)。</span><span class="sxs-lookup"><span data-stu-id="a751b-121">The name of the key is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="a751b-122">レジストリ キーからの読み取り権限がユーザーにない場合 (<xref:System.Security.SecurityException>)。</span><span class="sxs-lookup"><span data-stu-id="a751b-122">The user does not have permissions to read from registry keys (<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="a751b-123">キー名が 255 文字の制限を超えている場合 (<xref:System.ArgumentException>)。</span><span class="sxs-lookup"><span data-stu-id="a751b-123">The key name exceeds the 255-character limit (<xref:System.ArgumentException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="a751b-124">.NET Framework のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="a751b-124">.NET Framework Security</span></span>  

 <span data-ttu-id="a751b-125">このプロセスを実行するには、アセンブリに対して <xref:System.Security.Permissions.RegistryPermission> クラスで特権レベルが許可されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a751b-125">To run this process, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.RegistryPermission> class.</span></span> <span data-ttu-id="a751b-126">部分的に信頼されたコンテキストで実行している場合、プロセスは、特権がないために例外をスローする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a751b-126">If you are running in a partial-trust context, the process might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="a751b-127">同様に、ユーザーには、設定に対する作成や書き込みを行うための適切な ACL が必要です。</span><span class="sxs-lookup"><span data-stu-id="a751b-127">Similarly, the user must have the correct ACLs for creating or writing to settings.</span></span> <span data-ttu-id="a751b-128">たとえば、コード アクセス セキュリティのアクセス許可を持つローカル アプリケーションには、オペレーティング システムのアクセス許可がない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a751b-128">For example, a local application that has the code access security permission might not have operating system permission.</span></span> <span data-ttu-id="a751b-129">詳しくは、「[コード アクセス セキュリティの基礎](../../../../framework/misc/code-access-security-basics.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a751b-129">For more information, see [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a751b-130">参照</span><span class="sxs-lookup"><span data-stu-id="a751b-130">See also</span></span>

- <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>
- <xref:Microsoft.Win32.RegistryHive>
- [<span data-ttu-id="a751b-131">レジストリからの読み取りとレジストリへの書き込み</span><span class="sxs-lookup"><span data-stu-id="a751b-131">Reading from and Writing to the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)
