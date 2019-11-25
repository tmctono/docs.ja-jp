---
title: Microsoft.Win32 名前空間を使用したレジストリの読み取りと書き込み
ms.date: 07/20/2015
helpviewer_keywords:
- registry [Visual Basic]
ms.assetid: 4a0dcce0-c27b-4199-baa8-ee4528da6a56
ms.openlocfilehash: 841344186b8e56717b81e90397aabc608bdc6dab
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345499"
---
# <a name="reading-from-and-writing-to-the-registry-using-the-microsoftwin32-namespace-visual-basic"></a><span data-ttu-id="7a5a2-102">Microsoft.Win32 名前空間を使用したレジストリの読み取りと書き込み (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7a5a2-102">Reading from and Writing to the Registry Using the Microsoft.Win32 Namespace (Visual Basic)</span></span>

<span data-ttu-id="7a5a2-103">レジストリに対してプログラミングする際の基本的なニーズには `My.Computer.Registry` で対応できますが、.NET Framework の <xref:Microsoft.Win32> 名前空間の <xref:Microsoft.Win32.Registry> クラスと <xref:Microsoft.Win32.RegistryKey> クラスを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="7a5a2-103">Although `My.Computer.Registry` should cover your basic needs when programming against the registry, you can also use the <xref:Microsoft.Win32.Registry> and <xref:Microsoft.Win32.RegistryKey> classes in the <xref:Microsoft.Win32> namespace of the .NET Framework.</span></span>  
  
## <a name="keys-in-the-registry-class"></a><span data-ttu-id="7a5a2-104">Registry クラスのキー</span><span class="sxs-lookup"><span data-stu-id="7a5a2-104">Keys in the Registry Class</span></span>  

 <span data-ttu-id="7a5a2-105"><xref:Microsoft.Win32.Registry> クラスでは、サブキーとその値にアクセスするために使用できるベース レジストリ キーが提供されます。</span><span class="sxs-lookup"><span data-stu-id="7a5a2-105">The <xref:Microsoft.Win32.Registry> class supplies the base registry keys that can be used to access subkeys and their values.</span></span> <span data-ttu-id="7a5a2-106">ベース キー自体は読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="7a5a2-106">The base keys themselves are read-only.</span></span> <span data-ttu-id="7a5a2-107">次の表では、<xref:Microsoft.Win32.Registry> クラスによって公開される 7 つのキーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7a5a2-107">The following table lists and describes the seven keys exposed by the <xref:Microsoft.Win32.Registry> class.</span></span>  
  
|<span data-ttu-id="7a5a2-108">**Key**</span><span class="sxs-lookup"><span data-stu-id="7a5a2-108">**Key**</span></span>|<span data-ttu-id="7a5a2-109">**説明**</span><span class="sxs-lookup"><span data-stu-id="7a5a2-109">**Description**</span></span>|  
|-------------|---------------------|  
|<xref:Microsoft.Win32.Registry.ClassesRoot>|<span data-ttu-id="7a5a2-110">ドキュメントの種類と、それらの種類に関連付けられているプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="7a5a2-110">Defines the types of documents and the properties associated with those types.</span></span>|  
|<xref:Microsoft.Win32.Registry.CurrentConfig>|<span data-ttu-id="7a5a2-111">ユーザー固有ではないハードウェア構成情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7a5a2-111">Contains hardware configuration information that is not user-specific.</span></span>|  
|<xref:Microsoft.Win32.Registry.CurrentUser>|<span data-ttu-id="7a5a2-112">環境変数など、現在のユーザー設定に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7a5a2-112">Contains information about the current user preferences, such as environmental variables.</span></span>|  
|<xref:Microsoft.Win32.Registry.DynData>|<span data-ttu-id="7a5a2-113">仮想デバイス ドライバーによって使用されるデータなど、動的なレジストリ データが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7a5a2-113">Contains dynamic registry data, such as that used by Virtual Device Drivers.</span></span>|  
|<xref:Microsoft.Win32.Registry.LocalMachine>|<span data-ttu-id="7a5a2-114">ローカル コンピューターの構成データを保持する 5 つのサブキー (Hardware、SAM、Security、Software、System) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7a5a2-114">Contains five subkeys (Hardware, SAM, Security, Software, and System) that hold the configuration data for the local computer.</span></span>|  
|<xref:Microsoft.Win32.Registry.PerformanceData>|<span data-ttu-id="7a5a2-115">ソフトウェア コンポーネントのパフォーマンス情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7a5a2-115">Contains performance information for software components.</span></span>|  
|<xref:Microsoft.Win32.Registry.Users>|<span data-ttu-id="7a5a2-116">既定のユーザー設定についての情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7a5a2-116">Contains information about the default user preferences.</span></span>|  
  
> [!IMPORTANT]
> <span data-ttu-id="7a5a2-117">ローカル コンピューター (<xref:Microsoft.Win32.Registry.LocalMachine>) よりも、現在のユーザー (<xref:Microsoft.Win32.Registry.CurrentUser>) にデータを書き込む方が安全です。</span><span class="sxs-lookup"><span data-stu-id="7a5a2-117">It is more secure to write data to the current user (<xref:Microsoft.Win32.Registry.CurrentUser>) than to the local computer (<xref:Microsoft.Win32.Registry.LocalMachine>).</span></span> <span data-ttu-id="7a5a2-118">作成しようとするキーが、以前に悪意のある可能性のある別のプロセスによって作成されたことがある場合、一般に "スクワッティング" と呼ばれる状況が発生します。</span><span class="sxs-lookup"><span data-stu-id="7a5a2-118">A condition that's typically referred to as "squatting" occurs when the key you are creating was previously created by another, possibly malicious, process.</span></span> <span data-ttu-id="7a5a2-119">スクワッティングの発生を防ぐには、キーがまだ存在しない場合は `Nothing` を返す <xref:Microsoft.Win32.RegistryKey.GetValue%2A> などのメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="7a5a2-119">To prevent this from occurring, use a method, such as <xref:Microsoft.Win32.RegistryKey.GetValue%2A>, that returns `Nothing` if the key does not already exist.</span></span>  
  
## <a name="reading-a-value-from-the-registry"></a><span data-ttu-id="7a5a2-120">レジストリから値を読み取る</span><span class="sxs-lookup"><span data-stu-id="7a5a2-120">Reading a Value from the Registry</span></span>  

 <span data-ttu-id="7a5a2-121">次のコードでは、HKEY_CURRENT_USER から文字列を読み取る方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7a5a2-121">The following code shows how to read a string from HKEY_CURRENT_USER.</span></span>  
  
 [!code-vb[VbResourceTasks#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#20)]  
  
 <span data-ttu-id="7a5a2-122">次のコードは、HKEY_CURRENT_USER から文字列を読み取り、値を増分した後、書き込みます。</span><span class="sxs-lookup"><span data-stu-id="7a5a2-122">The following code reads, increments, and then writes a string to HKEY_CURRENT_USER.</span></span>  
  
 [!code-vb[VbResourceTasks#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="7a5a2-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="7a5a2-123">See also</span></span>

- <xref:System.SystemException>
- <xref:System.ApplicationException>
- <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>
- [<span data-ttu-id="7a5a2-124">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="7a5a2-124">Try...Catch...Finally Statement</span></span>](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="7a5a2-125">レジストリからの読み取りとレジストリへの書き込み</span><span class="sxs-lookup"><span data-stu-id="7a5a2-125">Reading from and Writing to the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)
- [<span data-ttu-id="7a5a2-126">セキュリティとレジストリ</span><span class="sxs-lookup"><span data-stu-id="7a5a2-126">Security and the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)
