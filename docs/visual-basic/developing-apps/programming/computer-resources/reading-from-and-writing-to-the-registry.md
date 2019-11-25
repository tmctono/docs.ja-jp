---
title: レジストリからの読み取りとレジストリへの書き込み
ms.date: 07/20/2015
helpviewer_keywords:
- My.Computer.Registry object, tasks
- registry [Visual Basic], writing to
- registry [Visual Basic], reading
ms.assetid: a13da106-185b-41d7-b23c-416da65e21e4
ms.openlocfilehash: 89db9ef9db4235c069d6239d32e4f8679fbabf0b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349760"
---
# <a name="reading-from-and-writing-to-the-registry-visual-basic"></a><span data-ttu-id="d1e83-102">レジストリからの読み取りとレジストリへの書き込み (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d1e83-102">Reading from and Writing to the Registry (Visual Basic)</span></span>

<span data-ttu-id="d1e83-103">このトピックでは、レジストリに関連するタスクおよび概念説明のトピックについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d1e83-103">This topic describes task and conceptual topics that are associated with the registry.</span></span>  
  
 <span data-ttu-id="d1e83-104">Visual Basic のプログラミングでは、レジストリへのアクセスには、Visual Basic に用意されている関数を使用する方法と、.NET Framework のレジストリ クラスを使用する方法のいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="d1e83-104">When programming in Visual Basic, you can choose to access the registry by means of either the functions provided by Visual Basic or the registry classes of the .NET Framework.</span></span> <span data-ttu-id="d1e83-105">レジストリは、オペレーティング システムからの情報と、コンピューターにホストされるアプリケーションからの情報をホストします。</span><span class="sxs-lookup"><span data-stu-id="d1e83-105">The registry hosts information from the operating system as well as information from applications hosted on the machine.</span></span> <span data-ttu-id="d1e83-106">レジストリを操作すると、システム リソースや保護情報への不適切なアクセスが許可され、セキュリティが損なわれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d1e83-106">Working with the registry may compromise security by allowing inappropriate access to system resources or protected information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d1e83-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d1e83-107">In This Section</span></span>  

 [<span data-ttu-id="d1e83-108">方法: レジストリ キーを作成し、その値を設定する</span><span class="sxs-lookup"><span data-stu-id="d1e83-108">How to: Create a Registry Key and Set Its Value</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-create-a-registry-key-and-set-its-value.md)  
 <span data-ttu-id="d1e83-109">`My.Computer.Registry` オブジェクトの `CreateSubKey` および `SetValue` メソッドを使用して、レジストリ キーを作成し、その値を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d1e83-109">Describes how to use the `CreateSubKey` and `SetValue` methods of the `My.Computer.Registry` object to create a registry key and set its value.</span></span>  
  
 [<span data-ttu-id="d1e83-110">方法: レジストリ キーから値を読み取る</span><span class="sxs-lookup"><span data-stu-id="d1e83-110">How to: Read a Value from a Registry Key</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-read-a-value-from-a-registry-key.md)  
 <span data-ttu-id="d1e83-111">`My.Computer.Registry` オブジェクトの `GetValue` メソッドを使用して、レジストリ キーから値を読み取る方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d1e83-111">Describes how to use the `GetValue` method of the `My.Computer.Registry` object to read a value from a registry key.</span></span>  
  
 [<span data-ttu-id="d1e83-112">方法: レジストリ キーの削除</span><span class="sxs-lookup"><span data-stu-id="d1e83-112">How to: Delete a Registry Key</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-delete-a-registry-key.md)  
 <span data-ttu-id="d1e83-113">`My.Computer.Registry.CurrentUser` プロパティの `DeleteSubKey` メソッドを使用して、レジストリ キーを削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d1e83-113">Describes how to use the `DeleteSubKey` method of the `My.Computer.Registry.CurrentUser` property to delete a registry key.</span></span>  
  
 [<span data-ttu-id="d1e83-114">Microsoft.Win32 名前空間を使用したレジストリの読み取りと書き込み</span><span class="sxs-lookup"><span data-stu-id="d1e83-114">Reading from and Writing to the Registry Using the Microsoft.Win32 Namespace</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry-using-the-microsoft-win32-namespace.md)  
 <span data-ttu-id="d1e83-115">.NET Framework の `Registry` および `RegistryKey` クラスを使用して、レジストリにアクセスする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d1e83-115">Describes how to use the `Registry` and `RegistryKey` classes of the .NET Framework to access the registry.</span></span>  
  
 [<span data-ttu-id="d1e83-116">セキュリティとレジストリ</span><span class="sxs-lookup"><span data-stu-id="d1e83-116">Security and the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)  
 <span data-ttu-id="d1e83-117">レジストリに関連するセキュリティの問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="d1e83-117">Discusses security issues involving the registry.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d1e83-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="d1e83-118">Related Sections</span></span>  

 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>  
 <span data-ttu-id="d1e83-119">`My.Computer.Registry` オブジェクトのメンバーをリストして説明します。</span><span class="sxs-lookup"><span data-stu-id="d1e83-119">Lists and explains members of the `My.Computer.Registry` object.</span></span>  
  
 <xref:Microsoft.Win32.Registry>  
 <span data-ttu-id="d1e83-120">`Registry` クラスの概要と、個々のキーおよびメンバーへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="d1e83-120">Presents an overview of the `Registry` class, along with links to individual keys and members.</span></span>
