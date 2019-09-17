---
title: Visual Studio で LINQ to DataSet プロジェクトを作成する
ms.date: 08/15/2018
ms.assetid: 49ba6cb0-cdd2-4571-aeaa-25bf0f40e9b3
ms.openlocfilehash: 8b905c65575c3c567459d843b2a5d1606bc63228
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783779"
---
# <a name="how-to-create-a-linq-to-dataset-project-in-visual-studio"></a><span data-ttu-id="aea3f-102">方法: Visual Studio で LINQ to DataSet プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="aea3f-102">How to: Create a LINQ to DataSet project In Visual Studio</span></span>

<span data-ttu-id="aea3f-103">LINQ プロジェクトの種類によっては、特定のアセンブリ参照とインポートされた名前空間C#(Visual Basic) または [using](../../../csharp/language-reference/keywords/using-directive.md) ディレクティブ () が必要になります。</span><span class="sxs-lookup"><span data-stu-id="aea3f-103">The different types of LINQ projects require certain assembly references and imported namespaces (Visual Basic) or [using](../../../csharp/language-reference/keywords/using-directive.md) directives (C#).</span></span> <span data-ttu-id="aea3f-104">LINQ の最小要件*は、の system.object への*参照と`using`の<xref:System.Linq>ディレクティブです。</span><span class="sxs-lookup"><span data-stu-id="aea3f-104">The minimum requirement for LINQ is a reference to *System.Core.dll* and a `using` directive for <xref:System.Linq>.</span></span>

<span data-ttu-id="aea3f-105">これらの要件は、Visual Studio 2017 で新しいC#コンソールアプリプロジェクトを作成した場合に既定で提供されます。</span><span class="sxs-lookup"><span data-stu-id="aea3f-105">These requirements are supplied by default if you create a new C# console app project in Visual Studio 2017.</span></span> <span data-ttu-id="aea3f-106">以前のバージョンの Visual Studio からプロジェクトをアップグレードする場合は、これらの LINQ 関連の参照を手動で指定することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="aea3f-106">If you're upgrading a project from an earlier version of Visual Studio, you might have to supply these LINQ-related references manually.</span></span>

<span data-ttu-id="aea3f-107">LINQ to DataSet*には、次の 2*つの追加の参照が必要*です。*</span><span class="sxs-lookup"><span data-stu-id="aea3f-107">LINQ to DataSet requires two additional references to *System.Data.dll* and *System.Data.DataSetExtensions.dll*.</span></span>

> [!NOTE]
> <span data-ttu-id="aea3f-108">コマンドプロンプトからビルドする場合は、 *%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.5*で LINQ 関連の dll を手動で参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aea3f-108">If you're building from a command prompt, you must manually reference the LINQ-related DLLs in *%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.5*.</span></span>

## <a name="to-enable-linq-to-dataset-functionality"></a><span data-ttu-id="aea3f-109">LINQ to DataSet 機能を有効にするには</span><span class="sxs-lookup"><span data-stu-id="aea3f-109">To enable LINQ to DataSet functionality</span></span>

<span data-ttu-id="aea3f-110">既存のプロジェクトで LINQ to DataSet 機能を有効にするには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="aea3f-110">Follow these steps to enable LINQ to DataSet functionality in an existing project.</span></span>

1. <span data-ttu-id="aea3f-111">**System. Core**、system.string、および**datasetextensions** **への参照**を追加します。</span><span class="sxs-lookup"><span data-stu-id="aea3f-111">Add references to **System.Core**, **System.Data**, and **System.Data.DataSetExtensions**.</span></span>

   <span data-ttu-id="aea3f-112">**ソリューションエクスプローラー**で、 **[参照]** ノードを右クリックし、 **[参照の追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aea3f-112">In **Solution Explorer**, right-click on the **References** node and select **Add Reference**.</span></span> <span data-ttu-id="aea3f-113">**[参照マネージャー]** ダイアログボックスで、 **[Core**]、 **[システムデータ]** 、および **[データ拡張子]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aea3f-113">In the **Reference Manager** dialog box, select **System.Core**, **System.Data**, and **System.Data.DataSetExtensions**.</span></span> <span data-ttu-id="aea3f-114">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aea3f-114">Select **OK**.</span></span>

1. <span data-ttu-id="aea3f-115">[Using](../../../csharp/language-reference/keywords/using-directive.md)ディレクティブ (または Visual Basic 内の[Imports ステートメント](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md))**を system.string および system.string**に**追加します。**</span><span class="sxs-lookup"><span data-stu-id="aea3f-115">Add [using](../../../csharp/language-reference/keywords/using-directive.md) directives (or [Imports statements](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) in Visual Basic) for **System.Data** and **System.Linq**.</span></span>

   ```csharp
   using System.Data;
   using System.Linq;
   ```

1. <span data-ttu-id="aea3f-116">必要に応じて`using` 、データベースへ`Imports`の接続方法に応じ**て、** **システム**のディレクティブ (またはステートメント) を追加します。</span><span class="sxs-lookup"><span data-stu-id="aea3f-116">Optionally, add a `using` directive (or `Imports` statement) for **System.Data.Common** or **System.Data.SqlClient**, depending on how you connect to the database.</span></span>

## <a name="see-also"></a><span data-ttu-id="aea3f-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="aea3f-117">See also</span></span>

- [<span data-ttu-id="aea3f-118">LINQ to DataSet を使ってみる</span><span class="sxs-lookup"><span data-stu-id="aea3f-118">Get started with LINQ to DataSet</span></span>](getting-started-linq-to-dataset.md)
