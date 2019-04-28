---
title: '方法: フォント ファミリとフォントを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- font families [Windows Forms], constructing
- fonts [Windows Forms], constructing
ms.assetid: d3a4a223-9492-4b54-9afd-db1c31c3cefd
ms.openlocfilehash: 0a9dcd00d4bc3e64ae4fc9a1d4884fac18521825
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937970"
---
# <a name="how-to-construct-font-families-and-fonts"></a><span data-ttu-id="01280-102">方法: フォント ファミリとフォントを作成する</span><span class="sxs-lookup"><span data-stu-id="01280-102">How to: Construct Font Families and Fonts</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="01280-103">同じタイプフェイスがさまざまなスタイルでのフォントのフォント ファミリにグループ化します。</span><span class="sxs-lookup"><span data-stu-id="01280-103">groups fonts with the same typeface but different styles into font families.</span></span> <span data-ttu-id="01280-104">たとえば、Arial フォント ファミリには、次のフォントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="01280-104">For example, the Arial font family contains the following fonts:</span></span>  
  
- <span data-ttu-id="01280-105">Arial 通常</span><span class="sxs-lookup"><span data-stu-id="01280-105">Arial Regular</span></span>  
  
- <span data-ttu-id="01280-106">Arial 太字</span><span class="sxs-lookup"><span data-stu-id="01280-106">Arial Bold</span></span>  
  
- <span data-ttu-id="01280-107">Arial 斜体</span><span class="sxs-lookup"><span data-stu-id="01280-107">Arial Italic</span></span>  
  
- <span data-ttu-id="01280-108">Arial 太字斜体</span><span class="sxs-lookup"><span data-stu-id="01280-108">Arial Bold Italic</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="01280-109">フォームのファミリの 4 つのスタイルを使用します。 標準、太字、斜体と太字斜体します。</span><span class="sxs-lookup"><span data-stu-id="01280-109">uses four styles to form families: regular, bold, italic, and bold italic.</span></span> <span data-ttu-id="01280-110">など、形容詞*を絞り込む*と*丸め*スタイル; とは見なされませんではなく、ファミリ名の一部であります。</span><span class="sxs-lookup"><span data-stu-id="01280-110">Adjectives such as *narrow* and *rounded* are not considered styles; rather they are part of the family name.</span></span> <span data-ttu-id="01280-111">たとえば、ゴシックは、次のメンバーを持つフォント ファミリです。</span><span class="sxs-lookup"><span data-stu-id="01280-111">For example, Arial Narrow is a font family with the following members:</span></span>  
  
- <span data-ttu-id="01280-112">Arial 狭い通常</span><span class="sxs-lookup"><span data-stu-id="01280-112">Arial Narrow Regular</span></span>  
  
- <span data-ttu-id="01280-113">Arial ナロー太字</span><span class="sxs-lookup"><span data-stu-id="01280-113">Arial Narrow Bold</span></span>  
  
- <span data-ttu-id="01280-114">Arial 狭い斜体</span><span class="sxs-lookup"><span data-stu-id="01280-114">Arial Narrow Italic</span></span>  
  
- <span data-ttu-id="01280-115">Arial 狭い太字斜体</span><span class="sxs-lookup"><span data-stu-id="01280-115">Arial Narrow Bold Italic</span></span>  
  
 <span data-ttu-id="01280-116">テキストを描画する前に[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]、構築する必要がある、<xref:System.Drawing.FontFamily>オブジェクトと<xref:System.Drawing.Font>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="01280-116">Before you can draw text with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you need to construct a <xref:System.Drawing.FontFamily> object and a <xref:System.Drawing.Font> object.</span></span> <span data-ttu-id="01280-117"><xref:System.Drawing.FontFamily>オブジェクト (たとえば、Arial) 書体を指定して、<xref:System.Drawing.Font>オブジェクトは、サイズ、スタイル、および単位を指定します。</span><span class="sxs-lookup"><span data-stu-id="01280-117">The <xref:System.Drawing.FontFamily> object specifies the typeface (for example, Arial), and the <xref:System.Drawing.Font> object specifies the size, style, and units.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01280-118">例</span><span class="sxs-lookup"><span data-stu-id="01280-118">Example</span></span>  
 <span data-ttu-id="01280-119">次の例では、標準のスタイル、サイズが 16 ピクセルの Arial フォントを作成します。</span><span class="sxs-lookup"><span data-stu-id="01280-119">The following example constructs a regular style Arial font with a size of 16 pixels.</span></span> <span data-ttu-id="01280-120">次のコードに渡される最初の引数、<xref:System.Drawing.Font.%23ctor%2A>コンス トラクターは、<xref:System.Drawing.FontFamily>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="01280-120">In the following code, the first argument passed to the <xref:System.Drawing.Font.%23ctor%2A> constructor is the <xref:System.Drawing.FontFamily> object.</span></span> <span data-ttu-id="01280-121">2 番目の引数には、4 番目の引数によって識別される単位でのフォントのサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="01280-121">The second argument specifies the size of the font measured in units identified by the fourth argument.</span></span> <span data-ttu-id="01280-122">3 番目の引数は、スタイルを識別します。</span><span class="sxs-lookup"><span data-stu-id="01280-122">The third argument identifies the style.</span></span>  
  
 <span data-ttu-id="01280-123"><xref:System.Drawing.GraphicsUnit.Pixel> メンバーである、<xref:System.Drawing.GraphicsUnit>列挙型、および<xref:System.Drawing.FontStyle.Regular>のメンバーである、<xref:System.Drawing.FontStyle>列挙体。</span><span class="sxs-lookup"><span data-stu-id="01280-123"><xref:System.Drawing.GraphicsUnit.Pixel> is a member of the <xref:System.Drawing.GraphicsUnit> enumeration, and <xref:System.Drawing.FontStyle.Regular> is a member of the <xref:System.Drawing.FontStyle> enumeration.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.FontsAndText#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="01280-124">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="01280-124">Compiling the Code</span></span>  
 <span data-ttu-id="01280-125">前の例は、Windows フォームで使用するために設計されていて、<xref:System.Windows.Forms.PaintEventArgs> のパラメーターである `e`<xref:System.Windows.Forms.PaintEventHandler> を必要とします。</span><span class="sxs-lookup"><span data-stu-id="01280-125">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01280-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="01280-126">See also</span></span>

- [<span data-ttu-id="01280-127">フォントとテキストの使用</span><span class="sxs-lookup"><span data-stu-id="01280-127">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="01280-128">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="01280-128">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
