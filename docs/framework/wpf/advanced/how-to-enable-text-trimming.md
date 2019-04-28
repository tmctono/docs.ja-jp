---
title: '方法: テキストのトリミングを有効にする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF], trimming
- documents [WPF], trimming text
- trimming text [WPF]
ms.assetid: dd8c9191-d2be-45fd-9fb4-3c75b65578c5
ms.openlocfilehash: 25fff566868e792004a915fee195485c4a1f385f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776131"
---
# <a name="how-to-enable-text-trimming"></a><span data-ttu-id="f5ca0-102">方法: テキストのトリミングを有効にする</span><span class="sxs-lookup"><span data-stu-id="f5ca0-102">How to: Enable Text Trimming</span></span>

<span data-ttu-id="f5ca0-103">この例は、使用状況とで使用できる値の効果では、<xref:System.Windows.TextTrimming>列挙体。</span><span class="sxs-lookup"><span data-stu-id="f5ca0-103">This example demonstrates the usage and effects of the values available in the <xref:System.Windows.TextTrimming> enumeration.</span></span>

## <a name="example"></a><span data-ttu-id="f5ca0-104">例</span><span class="sxs-lookup"><span data-stu-id="f5ca0-104">Example</span></span>

<span data-ttu-id="f5ca0-105">次の例では、定義、<xref:System.Windows.Controls.TextBlock>を持つ要素、<xref:System.Windows.Controls.TextBlock.TextTrimming%2A>属性に設定します。</span><span class="sxs-lookup"><span data-stu-id="f5ca0-105">The following example defines a <xref:System.Windows.Controls.TextBlock> element with the <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> attribute set.</span></span>

[!code-xaml[TextTrimmingSnippets#_TextTrimmingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml#_texttrimmingxaml)]

<span data-ttu-id="f5ca0-106">対応する設定<xref:System.Windows.TextTrimming>次の例では、コード内のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="f5ca0-106">Setting the corresponding <xref:System.Windows.TextTrimming> property in code is demonstrated below.</span></span>

[!code-csharp[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml.cs#_texttrimmingsettexttrimming)]
[!code-vb[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextTrimmingSnippets/VisualBasic/Window1.xaml.vb#_texttrimmingsettexttrimming)]

<span data-ttu-id="f5ca0-107">テキストのトリミングの現在の 3 つのオプションがあります。**CharacterEllipsis**、 **WordEllipsis**、および**None**します。</span><span class="sxs-lookup"><span data-stu-id="f5ca0-107">There are currently three options for trimming text: **CharacterEllipsis**, **WordEllipsis**, and **None**.</span></span>

<span data-ttu-id="f5ca0-108">ときに<xref:System.Windows.Controls.TextBlock.TextTrimming%2A>に設定されている**CharacterEllipsis**テキストが切り取られ、トリミング エッジに最も近い文字に省略記号では継続します。</span><span class="sxs-lookup"><span data-stu-id="f5ca0-108">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **CharacterEllipsis**, text is trimmed and continued with an ellipsis at the character closest to the trimming edge.</span></span>  <span data-ttu-id="f5ca0-109">この設定では、トリミング境界により近い位置でテキストが切り取られます。ただし、単語の一部が切り取られる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f5ca0-109">This setting tends to trim text to fit more closely to the trimming boundary, but may result in words being partially trimmed.</span></span>  <span data-ttu-id="f5ca0-110">次の図では、この設定の効果を示しています、<xref:System.Windows.Controls.TextBlock>上記で定義された 1 つに似ています。</span><span class="sxs-lookup"><span data-stu-id="f5ca0-110">The following figure shows the effect of this setting on a <xref:System.Windows.Controls.TextBlock> similar to the one defined above.</span></span>

<span data-ttu-id="f5ca0-111">![例:TextTrimming.CharacterEllipsis](./media/texttrimming-character.png "TextTrimming_Character")</span><span class="sxs-lookup"><span data-stu-id="f5ca0-111">![Example: TextTrimming.CharacterEllipsis](./media/texttrimming-character.png "TextTrimming_Character")</span></span>

<span data-ttu-id="f5ca0-112">ときに<xref:System.Windows.Controls.TextBlock.TextTrimming%2A>に設定されている**WordEllipsis**テキストが切り取られ、トリミング エッジに最も近い最初の完全な単語の最後にある省略記号では継続します。</span><span class="sxs-lookup"><span data-stu-id="f5ca0-112">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **WordEllipsis**, text is trimmed and continued with an ellipsis at the end of the first full word closest to the trimming edge.</span></span>  <span data-ttu-id="f5ca0-113">この設定は、部分的に切り取らの単語は表示されませんが、テキストとして、トリミング エッジにできるだけ近くなる傾向があります、 **CharacterEllipsis**設定します。</span><span class="sxs-lookup"><span data-stu-id="f5ca0-113">This setting will not show partially trimmed words, but tends not to trim text as closely to the trimming edge as the **CharacterEllipsis** setting.</span></span>  <span data-ttu-id="f5ca0-114">次の図では、この設定の効果を示しています、<xref:System.Windows.Controls.TextBlock>上で定義します。</span><span class="sxs-lookup"><span data-stu-id="f5ca0-114">The following figure shows the effect of this setting on the <xref:System.Windows.Controls.TextBlock> defined above.</span></span>

<span data-ttu-id="f5ca0-115">![例:TextTrimming.WordEllipsis](./media/texttrimming-word.png "TextTrimming_Word")</span><span class="sxs-lookup"><span data-stu-id="f5ca0-115">![Example: TextTrimming.WordEllipsis](./media/texttrimming-word.png "TextTrimming_Word")</span></span>

<span data-ttu-id="f5ca0-116">ときに<xref:System.Windows.Controls.TextBlock.TextTrimming%2A>に設定されている**None**テキストのトリミングは実行されません。</span><span class="sxs-lookup"><span data-stu-id="f5ca0-116">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **None**, no text trimming is performed.</span></span>  <span data-ttu-id="f5ca0-117">この場合、テキストは親テキスト コンテナーの境界にトリミングされるだけです。</span><span class="sxs-lookup"><span data-stu-id="f5ca0-117">In this case, text is simply cropped to the boundary of the parent text container.</span></span>  <span data-ttu-id="f5ca0-118">次の図では、この設定の効果を示しています、<xref:System.Windows.Controls.TextBlock>上記で定義された 1 つに似ています。</span><span class="sxs-lookup"><span data-stu-id="f5ca0-118">The following figure shows the effect of this setting on a <xref:System.Windows.Controls.TextBlock> similar to the one defined above.</span></span>

<span data-ttu-id="f5ca0-119">![例:TextTrimming.None](./media/texttrimming-none.png "TextTrimming_None")</span><span class="sxs-lookup"><span data-stu-id="f5ca0-119">![Example: TextTrimming.None](./media/texttrimming-none.png "TextTrimming_None")</span></span>
