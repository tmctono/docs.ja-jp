---
title: '方法: インストールされているフォントを列挙します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], enumerating installed
- examples [Windows Forms], fonts
ms.assetid: 26d74ef5-0f39-4eeb-8d20-00e66e014abe
ms.openlocfilehash: 34234ee0400e1d2ca36f2f559b63d282f590ca0d
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709885"
---
# <a name="how-to-enumerate-installed-fonts"></a><span data-ttu-id="9f5f0-102">方法: インストールされているフォントを列挙します。</span><span class="sxs-lookup"><span data-stu-id="9f5f0-102">How to: Enumerate Installed Fonts</span></span>
<span data-ttu-id="9f5f0-103"><xref:System.Drawing.Text.InstalledFontCollection>クラスから継承、<xref:System.Drawing.Text.FontCollection>抽象基本クラス。</span><span class="sxs-lookup"><span data-stu-id="9f5f0-103">The <xref:System.Drawing.Text.InstalledFontCollection> class inherits from the <xref:System.Drawing.Text.FontCollection> abstract base class.</span></span> <span data-ttu-id="9f5f0-104">使用することができます、<xref:System.Drawing.Text.InstalledFontCollection>コンピューターにインストールされているフォントを列挙するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="9f5f0-104">You can use an <xref:System.Drawing.Text.InstalledFontCollection> object to enumerate the fonts installed on the computer.</span></span> <span data-ttu-id="9f5f0-105"><xref:System.Drawing.Text.FontCollection.Families%2A>のプロパティ、<xref:System.Drawing.Text.InstalledFontCollection>オブジェクトの配列は、<xref:System.Drawing.FontFamily>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="9f5f0-105">The <xref:System.Drawing.Text.FontCollection.Families%2A> property of an <xref:System.Drawing.Text.InstalledFontCollection> object is an array of <xref:System.Drawing.FontFamily> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f5f0-106">例</span><span class="sxs-lookup"><span data-stu-id="9f5f0-106">Example</span></span>  
 <span data-ttu-id="9f5f0-107">次の例では、コンピューターにインストールされているすべてのフォント ファミリの名前が一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="9f5f0-107">The following example lists the names of all the font families installed on the computer.</span></span> <span data-ttu-id="9f5f0-108">コードを取得、<xref:System.Drawing.FontFamily.Name%2A>の各プロパティ<xref:System.Drawing.FontFamily>によって返される配列内のオブジェクト、<xref:System.Drawing.Text.FontCollection.Families%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="9f5f0-108">The code retrieves the <xref:System.Drawing.FontFamily.Name%2A> property of each <xref:System.Drawing.FontFamily> object in the array returned by the <xref:System.Drawing.Text.FontCollection.Families%2A> property.</span></span> <span data-ttu-id="9f5f0-109">ファミリ名を取得するには、フォームのコンマ区切りの一覧に連結されます。</span><span class="sxs-lookup"><span data-stu-id="9f5f0-109">As the family names are retrieved, they are concatenated to form a comma-separated list.</span></span> <span data-ttu-id="9f5f0-110">次に、<xref:System.Drawing.Graphics.DrawString%2A>のメソッド、<xref:System.Drawing.Graphics>クラスは、四角形で、コンマ区切りの一覧を描画します。</span><span class="sxs-lookup"><span data-stu-id="9f5f0-110">Then the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class draws the comma-separated list in a rectangle.</span></span>  
  
 <span data-ttu-id="9f5f0-111">コード例を実行する場合、出力に次の図に示すようなになります。</span><span class="sxs-lookup"><span data-stu-id="9f5f0-111">If you run the example code, the output will be similar to that shown in the following illustration.</span></span>  
  
 <span data-ttu-id="9f5f0-112">![フォントがインストールされている](./media/csfontstext6.png "csfontstext6")</span><span class="sxs-lookup"><span data-stu-id="9f5f0-112">![Installed Fonts](./media/csfontstext6.png "csfontstext6")</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.FontsAndText#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9f5f0-113">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="9f5f0-113">Compiling the Code</span></span>  
 <span data-ttu-id="9f5f0-114">前の例は、Windows フォームで使用するために設計されていて、<xref:System.Windows.Forms.PaintEventHandler> のパラメーターである <xref:System.Windows.Forms.PaintEventArgs> `e` を必要とします。</span><span class="sxs-lookup"><span data-stu-id="9f5f0-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span> <span data-ttu-id="9f5f0-115">さらに、インポートする必要があります、<xref:System.Drawing.Text>名前空間。</span><span class="sxs-lookup"><span data-stu-id="9f5f0-115">In addition, you should import the <xref:System.Drawing.Text> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f5f0-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="9f5f0-116">See also</span></span>
- [<span data-ttu-id="9f5f0-117">フォントとテキストの使用</span><span class="sxs-lookup"><span data-stu-id="9f5f0-117">Using Fonts and Text</span></span>](using-fonts-and-text.md)
