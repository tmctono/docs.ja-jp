---
title: LINQ to DataSet プロジェクトで Visual Studio を作成します。
ms.date: 08/15/2018
ms.assetid: 49ba6cb0-cdd2-4571-aeaa-25bf0f40e9b3
ms.openlocfilehash: 22763d3b9581d09d7bdda0c09480f8d36bb8e2ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667049"
---
# <a name="how-to-create-a-linq-to-dataset-project-in-visual-studio"></a><span data-ttu-id="0b7ae-102">方法: LINQ to DataSet プロジェクトで Visual Studio を作成します。</span><span class="sxs-lookup"><span data-stu-id="0b7ae-102">How to: Create a LINQ to DataSet project In Visual Studio</span></span>

<span data-ttu-id="0b7ae-103">LINQ プロジェクトの種類は、特定のアセンブリ参照とインポートされた名前空間 (Visual Basic) が必要です。 または[を使用して](../../../csharp/language-reference/keywords/using-directive.md)ディレクティブ (c#)。</span><span class="sxs-lookup"><span data-stu-id="0b7ae-103">The different types of LINQ projects require certain assembly references and imported namespaces (Visual Basic) or [using](../../../csharp/language-reference/keywords/using-directive.md) directives (C#).</span></span> <span data-ttu-id="0b7ae-104">LINQ の最低要件への参照を*System.Core.dll*と`using`ディレクティブを<xref:System.Linq>します。</span><span class="sxs-lookup"><span data-stu-id="0b7ae-104">The minimum requirement for LINQ is a reference to *System.Core.dll* and a `using` directive for <xref:System.Linq>.</span></span>

<span data-ttu-id="0b7ae-105">これらの要件は、Visual Studio 2017 で新しい c# コンソール アプリ プロジェクトを作成する場合に、既定で提供されます。</span><span class="sxs-lookup"><span data-stu-id="0b7ae-105">These requirements are supplied by default if you create a new C# console app project in Visual Studio 2017.</span></span> <span data-ttu-id="0b7ae-106">プロジェクトを Visual Studio の以前のバージョンからアップグレードする場合は、これらの LINQ に関連する参照を手動で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b7ae-106">If you're upgrading a project from an earlier version of Visual Studio, you might have to supply these LINQ-related references manually.</span></span>

<span data-ttu-id="0b7ae-107">LINQ to DataSet を 2 つの他の参照を必要と*System.Data.dll*と*System.Data.DataSetExtensions.dll*します。</span><span class="sxs-lookup"><span data-stu-id="0b7ae-107">LINQ to DataSet requires two additional references to *System.Data.dll* and *System.Data.DataSetExtensions.dll*.</span></span>

> [!NOTE]
> <span data-ttu-id="0b7ae-108">コマンド プロンプトから構築する場合は、LINQ 関連の Dll を手動で参照する必要があります *%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.5*します。</span><span class="sxs-lookup"><span data-stu-id="0b7ae-108">If you're building from a command prompt, you must manually reference the LINQ-related DLLs in *%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.5*.</span></span>

## <a name="to-enable-linq-to-dataset-functionality"></a><span data-ttu-id="0b7ae-109">LINQ to DataSet 機能を有効にするには</span><span class="sxs-lookup"><span data-stu-id="0b7ae-109">To enable LINQ to DataSet functionality</span></span>

<span data-ttu-id="0b7ae-110">LINQ を既存のプロジェクトで DataSet 機能を有効にする次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="0b7ae-110">Follow these steps to enable LINQ to DataSet functionality in an existing project.</span></span>

1. <span data-ttu-id="0b7ae-111">参照を追加**System.Core**、 **System.Data**、および**System.Data.DataSetExtensions**します。</span><span class="sxs-lookup"><span data-stu-id="0b7ae-111">Add references to **System.Core**, **System.Data**, and **System.Data.DataSetExtensions**.</span></span>

   <span data-ttu-id="0b7ae-112">**ソリューション エクスプ ローラー**を右クリックし、**参照**ノード**参照の追加**します。</span><span class="sxs-lookup"><span data-stu-id="0b7ae-112">In **Solution Explorer**, right-click on the **References** node and select **Add Reference**.</span></span> <span data-ttu-id="0b7ae-113">**参照マネージャー**ダイアログ ボックスで、 **System.Core**、 **System.Data**、および**System.Data.DataSetExtensions**します。</span><span class="sxs-lookup"><span data-stu-id="0b7ae-113">In the **Reference Manager** dialog box, select **System.Core**, **System.Data**, and **System.Data.DataSetExtensions**.</span></span> <span data-ttu-id="0b7ae-114">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0b7ae-114">Select **OK**.</span></span>

1. <span data-ttu-id="0b7ae-115">追加[を使用して](../../../csharp/language-reference/keywords/using-directive.md)ディレクティブ (または[Imports ステートメント](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)Visual basic) の**System.Data**と**System.Linq**します。</span><span class="sxs-lookup"><span data-stu-id="0b7ae-115">Add [using](../../../csharp/language-reference/keywords/using-directive.md) directives (or [Imports statements](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) in Visual Basic) for **System.Data** and **System.Linq**.</span></span>

   ```csharp
   using System.Data;
   using System.Linq;
   ```

1. <span data-ttu-id="0b7ae-116">必要に応じて、追加、`using`ディレクティブ (または`Imports`ステートメント) の**System.Data.Common**または**System.Data.SqlClient**データベースに接続する方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="0b7ae-116">Optionally, add a `using` directive (or `Imports` statement) for **System.Data.Common** or **System.Data.SqlClient**, depending on how you connect to the database.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b7ae-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="0b7ae-117">See also</span></span>

- [<span data-ttu-id="0b7ae-118">LINQ to DataSet を概要します。</span><span class="sxs-lookup"><span data-stu-id="0b7ae-118">Get started with LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)
