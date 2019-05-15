---
title: '方法: レジストリ キーを削除する (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.DeleteSetting
helpviewer_keywords:
- GetSetting function [Visual Basic]
- registry [Visual Basic], deleting values
- GetAllSettings function
- registry keys [Visual Basic], deleting
- registry [Visual Basic], deleting keys
- examples [Visual Basic], registry
ms.assetid: ab9aca0e-42b0-4ff7-8ff9-845a4bfdf9f2
ms.openlocfilehash: 2e0c8990fcc55bc4208b1c23690ff748b7167002
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662767"
---
# <a name="how-to-delete-a-registry-key-in-visual-basic"></a><span data-ttu-id="af811-102">方法: レジストリ キーを削除する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="af811-102">How to: Delete a Registry Key in Visual Basic</span></span>
<span data-ttu-id="af811-103"><xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%29> メソッドと <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%2CSystem.Boolean%29> メソッドはレジストリ キーの削除に使用できます。</span><span class="sxs-lookup"><span data-stu-id="af811-103">The <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%29> and <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%2CSystem.Boolean%29> methods can be used to delete registry keys.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="af811-104">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="af811-104">Procedure</span></span>  
  
#### <a name="to-delete-a-registry-key"></a><span data-ttu-id="af811-105">レジストリ キーを削除するには</span><span class="sxs-lookup"><span data-stu-id="af811-105">To delete a registry key</span></span>  
  
- <span data-ttu-id="af811-106">`DeleteSubKey` メソッドを使用して、レジストリ キーを削除します。</span><span class="sxs-lookup"><span data-stu-id="af811-106">Use the `DeleteSubKey` method to delete a registry key.</span></span> <span data-ttu-id="af811-107">この例では、CurrentUser ハイブの Software/TestApp キーを削除します。</span><span class="sxs-lookup"><span data-stu-id="af811-107">This example deletes the key Software/TestApp in the CurrentUser hive.</span></span> <span data-ttu-id="af811-108">このキーは、コード内で適切な文字列に変更したり、ユーザーが指定した情報を使用したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="af811-108">You can change this in the code to the appropriate string, or have it rely on user-supplied information.</span></span>  
  
     [!code-vb[VbResourceTasks#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#19)]  
  
## <a name="robust-programming"></a><span data-ttu-id="af811-109">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="af811-109">Robust Programming</span></span>  
 <span data-ttu-id="af811-110">キーと値の組み合わせが存在しない場合、`DeleteSubKey` メソッドは空の文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="af811-110">The `DeleteSubKey` method returns an empty string if the key/value pair does not exist.</span></span>  
  
 <span data-ttu-id="af811-111">次の条件を満たす場合は、例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="af811-111">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="af811-112">キーの名前が `Nothing` である場合 (<xref:System.ArgumentNullException>)。</span><span class="sxs-lookup"><span data-stu-id="af811-112">The name of the key is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="af811-113">レジストリ キーを作成するためのアクセス許可がユーザーにない場合 (<xref:System.Security.SecurityException>)。</span><span class="sxs-lookup"><span data-stu-id="af811-113">The user does not have permissions to delete registry keys (<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="af811-114">キー名が 255 文字の制限を超えている場合 (<xref:System.ArgumentException>)。</span><span class="sxs-lookup"><span data-stu-id="af811-114">The key name exceeds the 255-character limit (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="af811-115">レジストリ キーが読み取り専用の場合 (<xref:System.UnauthorizedAccessException>)。</span><span class="sxs-lookup"><span data-stu-id="af811-115">The registry key is read-only (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="af811-116">.NET Framework セキュリティ</span><span class="sxs-lookup"><span data-stu-id="af811-116">.NET Framework Security</span></span>  
 <span data-ttu-id="af811-117">必要なアクセス許可が実行時に与えられない (<xref:System.Security.Permissions.RegistryPermission>) 場合、またはユーザーが設定の作成や書き込みを行うための適切な (ACL によって決定された) アクセス権を持っていない場合、レジストリ呼び出しは失敗します。</span><span class="sxs-lookup"><span data-stu-id="af811-117">Registry calls fail if either sufficient run-time permissions are not granted (<xref:System.Security.Permissions.RegistryPermission>) or if the user does not have the correct access (as determined by the ACLs) for creating or writing to settings.</span></span> <span data-ttu-id="af811-118">たとえば、コード アクセス セキュリティのアクセス許可を持つローカル アプリケーションには、オペレーティング システムのアクセス許可がない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="af811-118">For example, a local application that has the code access security permission might not have operating system permission.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af811-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="af811-119">See also</span></span>

- <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A>
- <xref:Microsoft.Win32.RegistryKey>
- [<span data-ttu-id="af811-120">セキュリティとレジストリ</span><span class="sxs-lookup"><span data-stu-id="af811-120">Security and the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)
- [<span data-ttu-id="af811-121">レジストリからの読み取りとレジストリへの書き込み</span><span class="sxs-lookup"><span data-stu-id="af811-121">Reading from and Writing to the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)
