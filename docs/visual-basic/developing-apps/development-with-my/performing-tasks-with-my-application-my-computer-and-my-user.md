---
title: My.Application、My.Computer、および My.User でのタスクの実行
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application object [Visual Basic], developing applications
- rapid application development (RAD), My.Application
- rapid application development (RAD), My.Computer
- rapid application development (RAD), My.User
- My.Computer object [Visual Basic], developing applications
- My.User object [Visual Basic], developing applications
ms.assetid: c8af61bd-4dd3-4a0f-9af5-795b594b240b
ms.openlocfilehash: 55961d6857b690fc2726f541df8a5497a3207928
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411695"
---
# <a name="performing-tasks-with-myapplication-mycomputer-and-myuser-visual-basic"></a><span data-ttu-id="c9776-102">My.Application、My.Computer、および My.User でのタスクの実行 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c9776-102">Performing Tasks with My.Application, My.Computer, and My.User (Visual Basic)</span></span>

<span data-ttu-id="c9776-103">情報へのアクセスとよく使用される機能が提供される中心的な 3 つの `My` オブジェクトが、`My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>)、`My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>)、`My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>) です。</span><span class="sxs-lookup"><span data-stu-id="c9776-103">The three central `My` objects that provide access to information and commonly used functionality are `My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>), and `My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>).</span></span> <span data-ttu-id="c9776-104">これらのオブジェクトを使用してそれぞれ、現在のアプリケーション、アプリケーションがインストールされているコンピューター、またはアプリケーションの現在のユーザーに関連する情報にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c9776-104">You can use these objects to access information that is related to the current application, the computer that the application is installed on, or the current user of the application, respectively.</span></span>  
  
## <a name="myapplication-mycomputer-and-myuser"></a><span data-ttu-id="c9776-105">My.Application、My.Computer、My.User</span><span class="sxs-lookup"><span data-stu-id="c9776-105">My.Application, My.Computer, and My.User</span></span>  

 <span data-ttu-id="c9776-106">次の例は、`My` を使用して情報を取得する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c9776-106">The following examples demonstrate how information can be retrieved using `My`.</span></span>  
  
 [!code-vb[VbVbcnMy#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#1)]  
  
 [!code-vb[VbVbcnMy#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#2)]  
  
 <span data-ttu-id="c9776-107">情報を取得するだけでなく、これら 3 つのオブジェクトを使用して公開されるメンバーは、そのオブジェクトに関連するメソッドを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="c9776-107">In addition to retrieving information, the members exposed through these three objects also allow you to execute methods related to that object.</span></span> <span data-ttu-id="c9776-108">たとえば、`My.Computer` を使用して、さまざまなメソッドにアクセスして、ファイルの操作やレジストリの更新ができます。</span><span class="sxs-lookup"><span data-stu-id="c9776-108">For instance, you can access a variety of methods to manipulate files or update the registry through `My.Computer`.</span></span>  
  
 <span data-ttu-id="c9776-109">ファイル、ディレクトリ、およびドライブを操作するためのさまざまなメソッドとプロパティが含まれているため、`My` を使用するとファイル I/O が大幅に簡単で高速になります。</span><span class="sxs-lookup"><span data-stu-id="c9776-109">File I/O is significantly easier and faster with `My`, which includes a variety of methods and properties for manipulating files, directories, and drives.</span></span> <span data-ttu-id="c9776-110"><xref:Microsoft.VisualBasic.FileIO.TextFieldParser> オブジェクトを使用すると、区切り記号または固定幅フィールドが含まれる大規模な構造化ファイルから読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="c9776-110">The <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> object allows you to read from large structured files that have delimited or fixed-width fields.</span></span> <span data-ttu-id="c9776-111">この例では、`TextFieldParser` `reader` を開き、それを使用して `C:\TestFolder1\test1.txt` から読み取ります。</span><span class="sxs-lookup"><span data-stu-id="c9776-111">This example opens the `TextFieldParser` `reader` and uses it to read from `C:\TestFolder1\test1.txt`.</span></span>  
  
 [!code-vb[VbVbalrTextFieldParser#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTextFieldParser/VB/Class1.vb#23)]  
  
 <span data-ttu-id="c9776-112">`My.Application` アプリケーションを使用すると、アプリケーションのカルチャを変更できます。</span><span class="sxs-lookup"><span data-stu-id="c9776-112">`My.Application` allows you to change the culture for your application.</span></span> <span data-ttu-id="c9776-113">このメソッドを呼び出す方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="c9776-113">The following example demonstrates how this method can be called.</span></span>  
  
 [!code-vb[VbVbcnMy#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="c9776-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="c9776-114">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [<span data-ttu-id="c9776-115">プロジェクトの種類に応じた My の機能</span><span class="sxs-lookup"><span data-stu-id="c9776-115">How My Depends on Project Type</span></span>](how-my-depends-on-project-type.md)
