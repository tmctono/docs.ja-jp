---
title: '方法 : Visual Basic で XML ドキュメントを作成する'
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
ms.openlocfilehash: 5b317706e3e8e0c5958f5a3d0fd859d68600bc7a
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524492"
---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a><span data-ttu-id="8291e-102">方法 : Visual Basic で XML ドキュメントを作成する</span><span class="sxs-lookup"><span data-stu-id="8291e-102">How to: Create XML Documentation in Visual Basic</span></span>

<span data-ttu-id="8291e-103">この例では、XML ドキュメントコメントをコードに追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8291e-103">This example shows how to add XML documentation comments to your code.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-xml-documentation-for-a-type-or-member"></a><span data-ttu-id="8291e-104">型またはメンバーの XML ドキュメントを作成するには</span><span class="sxs-lookup"><span data-stu-id="8291e-104">To create XML documentation for a type or member</span></span>

1. <span data-ttu-id="8291e-105">**コードエディター**で、ドキュメントを作成する型またはメンバーの上の行にカーソルを置きます。</span><span class="sxs-lookup"><span data-stu-id="8291e-105">In the **Code Editor**, position your cursor on the line above the type or member for which you want to create documentation.</span></span>

2. <span data-ttu-id="8291e-106">「@No__t_0 (3 つの単一引用符)」と入力します。</span><span class="sxs-lookup"><span data-stu-id="8291e-106">Type `'''` (three single-quotation marks).</span></span>

    <span data-ttu-id="8291e-107">型またはメンバーの XML スケルトンが**コードエディター**に追加されます。</span><span class="sxs-lookup"><span data-stu-id="8291e-107">An XML skeleton for the type or member is added in the **Code Editor**.</span></span>

3. <span data-ttu-id="8291e-108">適切なタグの間に説明情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="8291e-108">Add descriptive information between the appropriate tags.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8291e-109">XML ドキュメントブロック内に行を追加する場合は、各行を `'''` で始める必要があります。</span><span class="sxs-lookup"><span data-stu-id="8291e-109">If you add additional lines within the XML documentation block, each line must begin with `'''`.</span></span>

4. <span data-ttu-id="8291e-110">新しい XML ドキュメントコメントと共に型またはメンバーを使用するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="8291e-110">Add additional code that uses the type or member with the new XML documentation comments.</span></span>

    <span data-ttu-id="8291e-111">IntelliSense では、型またはメンバーの \<summary > タグのテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8291e-111">IntelliSense displays the text from the \<summary> tag for the type or member.</span></span>

5. <span data-ttu-id="8291e-112">コードをコンパイルして、ドキュメントコメントを含む XML ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="8291e-112">Compile the code to generate an XML file containing the documentation comments.</span></span> <span data-ttu-id="8291e-113">詳細については、「[-doc](../../../visual-basic/reference/command-line-compiler/doc.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8291e-113">For more information, see [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8291e-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="8291e-114">See also</span></span>

- [<span data-ttu-id="8291e-115">XML の使用によるコードのドキュメントの作成</span><span class="sxs-lookup"><span data-stu-id="8291e-115">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [<span data-ttu-id="8291e-116">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="8291e-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
- [<span data-ttu-id="8291e-117">-doc</span><span class="sxs-lookup"><span data-stu-id="8291e-117">-doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)
