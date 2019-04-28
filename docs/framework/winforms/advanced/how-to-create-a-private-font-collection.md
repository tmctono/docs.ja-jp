---
title: '方法: プライベート フォント コレクションを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- private font collections [Windows Forms], creating
- fonts [Windows Forms], creating private collections
ms.assetid: 6533d5e5-a8dc-4b76-9fc4-3bf75c8b9212
ms.openlocfilehash: f78d48c88b72388676f5e7ae963b98d8f1b4beac
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937835"
---
# <a name="how-to-create-a-private-font-collection"></a><span data-ttu-id="f2876-102">方法: プライベート フォント コレクションを作成する</span><span class="sxs-lookup"><span data-stu-id="f2876-102">How to: Create a Private Font Collection</span></span>
<span data-ttu-id="f2876-103"><xref:System.Drawing.Text.PrivateFontCollection>クラスから継承、<xref:System.Drawing.Text.FontCollection>抽象基本クラス。</span><span class="sxs-lookup"><span data-stu-id="f2876-103">The <xref:System.Drawing.Text.PrivateFontCollection> class inherits from the <xref:System.Drawing.Text.FontCollection> abstract base class.</span></span> <span data-ttu-id="f2876-104">使用することができます、<xref:System.Drawing.Text.PrivateFontCollection>具体的には、アプリケーションのフォントのセットを保持するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f2876-104">You can use a <xref:System.Drawing.Text.PrivateFontCollection> object to maintain a set of fonts specifically for your application.</span></span> <span data-ttu-id="f2876-105">プライベート フォント コレクションには、インストールされているシステム フォントだけでなく、コンピューターにインストールされていないフォントを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f2876-105">A private font collection can include installed system fonts as well as fonts that have not been installed on the computer.</span></span> <span data-ttu-id="f2876-106">プライベート フォント コレクションには、フォント ファイルを追加するには、呼び出し、<xref:System.Drawing.Text.PrivateFontCollection.AddFontFile%2A>のメソッドを<xref:System.Drawing.Text.PrivateFontCollection>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f2876-106">To add a font file to a private font collection, call the <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile%2A> method of a <xref:System.Drawing.Text.PrivateFontCollection> object.</span></span>  
  
 <span data-ttu-id="f2876-107"><xref:System.Drawing.Text.FontCollection.Families%2A>のプロパティを<xref:System.Drawing.Text.PrivateFontCollection>オブジェクトには配列が含まれています<xref:System.Drawing.FontFamily>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f2876-107">The <xref:System.Drawing.Text.FontCollection.Families%2A> property of a <xref:System.Drawing.Text.PrivateFontCollection> object contains an array of <xref:System.Drawing.FontFamily> objects.</span></span>  
  
 <span data-ttu-id="f2876-108">プライベート フォント コレクション内のフォント ファミリの数は必ずしもコレクションに追加されたフォント ファイルの数と同じです。</span><span class="sxs-lookup"><span data-stu-id="f2876-108">The number of font families in a private font collection is not necessarily the same as the number of font files that have been added to the collection.</span></span> <span data-ttu-id="f2876-109">たとえば、ArialBd.tff、Times.tff、および TimesBd.tff ファイルをコレクションに追加するとします。</span><span class="sxs-lookup"><span data-stu-id="f2876-109">For example, suppose you add the files ArialBd.tff, Times.tff, and TimesBd.tff to a collection.</span></span> <span data-ttu-id="f2876-110">ありますが、3 つのファイル、コレクション内の 2 つだけのファミリ Times.tff と TimesBd.tff 同じファミリに属しているためです。</span><span class="sxs-lookup"><span data-stu-id="f2876-110">There will be three files but only two families in the collection because Times.tff and TimesBd.tff belong to the same family.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2876-111">例</span><span class="sxs-lookup"><span data-stu-id="f2876-111">Example</span></span>  
 <span data-ttu-id="f2876-112">次の例では、次の 3 つのフォント ファイルを<xref:System.Drawing.Text.PrivateFontCollection>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f2876-112">The following example adds the following three font files to a <xref:System.Drawing.Text.PrivateFontCollection> object:</span></span>  
  
- <span data-ttu-id="f2876-113">C:\\*systemroot*\Fonts\Arial.tff (Arial、正規表現)</span><span class="sxs-lookup"><span data-stu-id="f2876-113">C:\\*systemroot*\Fonts\Arial.tff (Arial, regular)</span></span>  
  
- <span data-ttu-id="f2876-114">C:\\*systemroot*\Fonts\CourBI.tff (Courier New、太字斜体)</span><span class="sxs-lookup"><span data-stu-id="f2876-114">C:\\*systemroot*\Fonts\CourBI.tff (Courier New, bold italic)</span></span>  
  
- <span data-ttu-id="f2876-115">C:\\*systemroot*\Fonts\TimesBd.tff (Times New Roman, bold)</span><span class="sxs-lookup"><span data-stu-id="f2876-115">C:\\*systemroot*\Fonts\TimesBd.tff (Times New Roman, bold)</span></span>  
  
 <span data-ttu-id="f2876-116">コードの配列を取得する<xref:System.Drawing.FontFamily>オブジェクトから、<xref:System.Drawing.Text.FontCollection.Families%2A>のプロパティ、<xref:System.Drawing.Text.PrivateFontCollection>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f2876-116">The code retrieves an array of <xref:System.Drawing.FontFamily> objects from the <xref:System.Drawing.Text.FontCollection.Families%2A> property of the <xref:System.Drawing.Text.PrivateFontCollection> object.</span></span>  
  
 <span data-ttu-id="f2876-117">各<xref:System.Drawing.FontFamily>コードでは、コレクション内のオブジェクト、<xref:System.Drawing.FontFamily.IsStyleAvailable%2A>するさまざまなスタイル (標準、太字、斜体、太字、斜体、下線、取り消し線) が使用できるかどうかを判断するメソッド。</span><span class="sxs-lookup"><span data-stu-id="f2876-117">For each <xref:System.Drawing.FontFamily> object in the collection, the code calls the <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> method to determine whether various styles (regular, bold, italic, bold italic, underline, and strikeout) are available.</span></span> <span data-ttu-id="f2876-118">渡される引数、<xref:System.Drawing.FontFamily.IsStyleAvailable%2A>メソッドのメンバーである、<xref:System.Drawing.FontStyle>列挙体。</span><span class="sxs-lookup"><span data-stu-id="f2876-118">The arguments passed to the <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> method are members of the <xref:System.Drawing.FontStyle> enumeration.</span></span>  
  
 <span data-ttu-id="f2876-119">指定されたファミリ/スタイルの組み合わせがある場合、<xref:System.Drawing.Font>そのファミリとスタイルを使用してオブジェクトを構築します。</span><span class="sxs-lookup"><span data-stu-id="f2876-119">If a given family/style combination is available, a <xref:System.Drawing.Font> object is constructed using that family and style.</span></span> <span data-ttu-id="f2876-120">渡される最初の引数、<xref:System.Drawing.Font.%23ctor%2A>コンス トラクターは、フォント ファミリ名 (いない、<xref:System.Drawing.FontFamily>オブジェクトの他のバリエーションの場合と同様、<xref:System.Drawing.Font.%23ctor%2A>コンス トラクター)。</span><span class="sxs-lookup"><span data-stu-id="f2876-120">The first argument passed to the <xref:System.Drawing.Font.%23ctor%2A> constructor is the font family name (not a <xref:System.Drawing.FontFamily> object as is the case for other variations of the <xref:System.Drawing.Font.%23ctor%2A> constructor).</span></span> <span data-ttu-id="f2876-121">後に、<xref:System.Drawing.Font>オブジェクトが構築されたに渡される、<xref:System.Drawing.Graphics.DrawString%2A>のメソッド、<xref:System.Drawing.Graphics>スタイルの名前と共に、ファミリ名を表示するクラス。</span><span class="sxs-lookup"><span data-stu-id="f2876-121">After the <xref:System.Drawing.Font> object is constructed, it is passed to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class to display the family name along with the name of the style.</span></span>  
  
 <span data-ttu-id="f2876-122">次のコードの出力は次の図に示すように出力になります。</span><span class="sxs-lookup"><span data-stu-id="f2876-122">The output of the following code is similar to the output shown in the following illustration:</span></span>  
  
 ![さまざまなフォントでテキストを示すスクリーン ショット。](./media/how-to-create-a-private-font-collection/various-fonts-text-output.png)  
  
 <span data-ttu-id="f2876-124">次のコード例では、プライベート フォント コレクションに追加された) Arial.tff は、Arial 標準スタイルのフォント ファイルです。</span><span class="sxs-lookup"><span data-stu-id="f2876-124">Arial.tff (which was added to the private font collection in the following code example) is the font file for the Arial regular style.</span></span> <span data-ttu-id="f2876-125">ただし、プログラムの出力が Arial フォント ファミリの標準以外の複数の使用可能なスタイルを表示することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f2876-125">Note, however, that the program output shows several available styles other than regular for the Arial font family.</span></span> <span data-ttu-id="f2876-126">だ[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]標準スタイルから太字、斜体、および太字斜体スタイルをシミュレートすることができます。</span><span class="sxs-lookup"><span data-stu-id="f2876-126">That is because [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] can simulate the bold, italic, and bold italic styles from the regular style.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="f2876-127">下線や標準のスタイルから取り消し線の生成もできます。</span><span class="sxs-lookup"><span data-stu-id="f2876-127">can also produce underlines and strikeouts from the regular style.</span></span>  
  
 <span data-ttu-id="f2876-128">同様に、[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]太字または斜体のスタイルのいずれかから太字斜体のスタイルをシミュレートすることができます。</span><span class="sxs-lookup"><span data-stu-id="f2876-128">Similarly, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] can simulate the bold italic style from either the bold style or the italic style.</span></span> <span data-ttu-id="f2876-129">プログラムの出力が TimesBd.tff (Times New Roman、太字) が唯一にもかかわらず太字斜体スタイルが回ファミリに使用できることを示しています、コレクション内の回ファイル。</span><span class="sxs-lookup"><span data-stu-id="f2876-129">The program output shows that the bold italic style is available for the Times family even though TimesBd.tff (Times New Roman, bold) is the only Times file in the collection.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.FontsAndText#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f2876-130">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="f2876-130">Compiling the Code</span></span>  
 <span data-ttu-id="f2876-131">前の例は、Windows フォームで使用するために設計されています。 また必要が<xref:System.Windows.Forms.PaintEventArgs> `e`、はのパラメーター<xref:System.Windows.Forms.PaintEventHandler>します。</span><span class="sxs-lookup"><span data-stu-id="f2876-131">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2876-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="f2876-132">See also</span></span>

- <xref:System.Drawing.Text.PrivateFontCollection>
- [<span data-ttu-id="f2876-133">フォントとテキストの使用</span><span class="sxs-lookup"><span data-stu-id="f2876-133">Using Fonts and Text</span></span>](using-fonts-and-text.md)
