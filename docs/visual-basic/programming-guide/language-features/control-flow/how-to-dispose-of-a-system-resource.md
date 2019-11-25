---
title: '方法 : システム リソースを破棄する'
ms.date: 07/20/2015
helpviewer_keywords:
- Using statement [Visual Basic], disposing of system resources
- Visual Basic code, control flow
- system resources, disposing of
- resources [Visual Basic], disposing of system
- system resources
- Using statement [Visual Basic], Using...End Using
- Using block
ms.assetid: 8be2b239-8090-419b-8e7e-bcaa75b0ecc8
ms.openlocfilehash: c493051050442597196ba484fb9ce8e99249dbb7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353944"
---
# <a name="how-to-dispose-of-a-system-resource-visual-basic"></a><span data-ttu-id="69af8-102">方法: システム リソースを破棄する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="69af8-102">How to: Dispose of a System Resource (Visual Basic)</span></span>
<span data-ttu-id="69af8-103">You can use a `Using` block to guarantee that the system disposes of a resource when your code exits the block.</span><span class="sxs-lookup"><span data-stu-id="69af8-103">You can use a `Using` block to guarantee that the system disposes of a resource when your code exits the block.</span></span> <span data-ttu-id="69af8-104">This is useful if you are using a system resource that consumes a large amount of memory, or that other components also want to use.</span><span class="sxs-lookup"><span data-stu-id="69af8-104">This is useful if you are using a system resource that consumes a large amount of memory, or that other components also want to use.</span></span>  
  
### <a name="to-dispose-of-a-database-connection-when-your-code-is-finished-with-it"></a><span data-ttu-id="69af8-105">To dispose of a database connection when your code is finished with it</span><span class="sxs-lookup"><span data-stu-id="69af8-105">To dispose of a database connection when your code is finished with it</span></span>  
  
1. <span data-ttu-id="69af8-106">Make sure you include the appropriate [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) for the database connection at the beginning of your source file (in this case, <xref:System.Data.SqlClient>).</span><span class="sxs-lookup"><span data-stu-id="69af8-106">Make sure you include the appropriate [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) for the database connection at the beginning of your source file (in this case, <xref:System.Data.SqlClient>).</span></span>  
  
2. <span data-ttu-id="69af8-107">Create a `Using` block with the `Using` and `End Using` statements.</span><span class="sxs-lookup"><span data-stu-id="69af8-107">Create a `Using` block with the `Using` and `End Using` statements.</span></span> <span data-ttu-id="69af8-108">Inside the block, put the code that deals with the database connection.</span><span class="sxs-lookup"><span data-stu-id="69af8-108">Inside the block, put the code that deals with the database connection.</span></span>  
  
3. <span data-ttu-id="69af8-109">Declare the connection and create an instance of it as part of the `Using` statement.</span><span class="sxs-lookup"><span data-stu-id="69af8-109">Declare the connection and create an instance of it as part of the `Using` statement.</span></span>  
  
    ```vb  
    ' Insert the following line at the beginning of your source file.  
    Imports System.Data.SqlClient  
    Public Sub AccessSql(ByVal s As String)  
        Using sqc As New System.Data.SqlClient.SqlConnection(s)  
            MsgBox("Connected with string """ & sqc.ConnectionString & """")  
        End Using  
    End Sub  
    ```  
  
     <span data-ttu-id="69af8-110">The system disposes of the resource no matter how you exit the block, including the case of an unhandled exception.</span><span class="sxs-lookup"><span data-stu-id="69af8-110">The system disposes of the resource no matter how you exit the block, including the case of an unhandled exception.</span></span>  
  
     <span data-ttu-id="69af8-111">Note that you cannot access `sqc` from outside the `Using` block, because its scope is limited to the block.</span><span class="sxs-lookup"><span data-stu-id="69af8-111">Note that you cannot access `sqc` from outside the `Using` block, because its scope is limited to the block.</span></span>  
  
     <span data-ttu-id="69af8-112">You can use this same technique on a system resource such as a file handle or a COM wrapper.</span><span class="sxs-lookup"><span data-stu-id="69af8-112">You can use this same technique on a system resource such as a file handle or a COM wrapper.</span></span> <span data-ttu-id="69af8-113">You use a `Using` block when you want to be sure to leave the resource available for other components after you have exited the `Using` block.</span><span class="sxs-lookup"><span data-stu-id="69af8-113">You use a `Using` block when you want to be sure to leave the resource available for other components after you have exited the `Using` block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69af8-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="69af8-114">See also</span></span>

- <xref:System.Data.SqlClient.SqlConnection>
- [<span data-ttu-id="69af8-115">制御フロー</span><span class="sxs-lookup"><span data-stu-id="69af8-115">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="69af8-116">条件判断構造</span><span class="sxs-lookup"><span data-stu-id="69af8-116">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="69af8-117">ループ構造</span><span class="sxs-lookup"><span data-stu-id="69af8-117">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="69af8-118">その他の制御構造</span><span class="sxs-lookup"><span data-stu-id="69af8-118">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [<span data-ttu-id="69af8-119">入れ子になった制御構造</span><span class="sxs-lookup"><span data-stu-id="69af8-119">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="69af8-120">Using ステートメント</span><span class="sxs-lookup"><span data-stu-id="69af8-120">Using Statement</span></span>](../../../../visual-basic/language-reference/statements/using-statement.md)
