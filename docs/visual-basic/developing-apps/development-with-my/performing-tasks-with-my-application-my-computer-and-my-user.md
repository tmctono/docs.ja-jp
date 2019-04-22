---
title: My.Application、My.Computer、および My.User でのタスクの実行 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application object [Visual Basic], developing applications
- rapid application development (RAD), My.Application
- rapid application development (RAD), My.Computer
- rapid application development (RAD), My.User
- My.Computer object [Visual Basic], developing applications
- My.User object [Visual Basic], developing applications
ms.assetid: c8af61bd-4dd3-4a0f-9af5-795b594b240b
ms.openlocfilehash: 0372fbf63f6d12e266674f92225183911aa4ca30
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58834050"
---
# <a name="performing-tasks-with-myapplication-mycomputer-and-myuser-visual-basic"></a><span data-ttu-id="e37fb-102">My.Application、My.Computer、および My.User でのタスクの実行 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e37fb-102">Performing Tasks with My.Application, My.Computer, and My.User (Visual Basic)</span></span>
<span data-ttu-id="e37fb-103">次の 3 つの中央`My`と一般的な情報へのアクセスで使用される機能を提供するオブジェクトが`My.Application`(<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>)、 `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>)、および`My.User`(<xref:Microsoft.VisualBasic.ApplicationServices.User>)。</span><span class="sxs-lookup"><span data-stu-id="e37fb-103">The three central `My` objects that provide access to information and commonly used functionality are `My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>), and `My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>).</span></span> <span data-ttu-id="e37fb-104">これらのオブジェクトを使用して、それぞれ、現在のアプリケーションや、アプリケーションがインストールされているコンピューター、アプリケーションの現在のユーザーに関連する情報にアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="e37fb-104">You can use these objects to access information that is related to the current application, the computer that the application is installed on, or the current user of the application, respectively.</span></span>  
  
## <a name="myapplication-mycomputer-and-myuser"></a><span data-ttu-id="e37fb-105">My.Application、My.Computer、および My.User</span><span class="sxs-lookup"><span data-stu-id="e37fb-105">My.Application, My.Computer, and My.User</span></span>  
 <span data-ttu-id="e37fb-106">次の例の情報をする方法を使用して取得`My`します。</span><span class="sxs-lookup"><span data-stu-id="e37fb-106">The following examples demonstrate how information can be retrieved using `My`.</span></span>  
  
 [!code-vb[VbVbcnMy#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#1)]  
  
 [!code-vb[VbVbcnMy#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#2)]  
  
 <span data-ttu-id="e37fb-107">情報を取得するだけでなくこれら 3 つのオブジェクトを通じて公開されるメンバーをすることもそのオブジェクトに関連するメソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e37fb-107">In addition to retrieving information, the members exposed through these three objects also allow you to execute methods related to that object.</span></span> <span data-ttu-id="e37fb-108">たとえば、さまざまなファイルを操作または経由でのレジストリを更新する方法をアクセスできる`My.Computer`します。</span><span class="sxs-lookup"><span data-stu-id="e37fb-108">For instance, you can access a variety of methods to manipulate files or update the registry through `My.Computer`.</span></span>  
  
 <span data-ttu-id="e37fb-109">簡単かつ迅速で、ファイル I/O が大幅に`My`さまざまなメソッドとファイル、ディレクトリ、およびドライブを操作するためのプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e37fb-109">File I/O is significantly easier and faster with `My`, which includes a variety of methods and properties for manipulating files, directories, and drives.</span></span> <span data-ttu-id="e37fb-110"><xref:Microsoft.VisualBasic.FileIO.TextFieldParser>オブジェクトは、大きな構造化されたファイルが区切られた、または固定幅フィールドから読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="e37fb-110">The <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> object allows you to read from large structured files that have delimited or fixed-width fields.</span></span> <span data-ttu-id="e37fb-111">この例を開いて、 `TextFieldParser` `reader`オブジェクトからの読み取りを使用して`C:\TestFolder1\test1.txt`します。</span><span class="sxs-lookup"><span data-stu-id="e37fb-111">This example opens the `TextFieldParser` `reader` and uses it to read from `C:\TestFolder1\test1.txt`.</span></span>  
  
 [!code-vb[VbVbalrTextFieldParser#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTextFieldParser/VB/Class1.vb#23)]  
  
 <span data-ttu-id="e37fb-112">`My.Application` アプリケーションのカルチャを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="e37fb-112">`My.Application` allows you to change the culture for your application.</span></span> <span data-ttu-id="e37fb-113">次の例では、このメソッドを呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e37fb-113">The following example demonstrates how this method can be called.</span></span>  
  
 [!code-vb[VbVbcnMy#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="e37fb-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="e37fb-114">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [<span data-ttu-id="e37fb-115">プロジェクトの種類に応じた My の機能</span><span class="sxs-lookup"><span data-stu-id="e37fb-115">How My Depends on Project Type</span></span>](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
