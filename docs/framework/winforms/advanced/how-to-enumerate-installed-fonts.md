---
title: '方法: インストールされているフォントを列挙する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], enumerating installed
- examples [Windows Forms], fonts
ms.assetid: 26d74ef5-0f39-4eeb-8d20-00e66e014abe
ms.openlocfilehash: 92f27399cce9e03a4679c8a34fbdafcf28c32252
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59155013"
---
# <a name="how-to-enumerate-installed-fonts"></a><span data-ttu-id="0d0b8-102">方法: インストールされているフォントを列挙する</span><span class="sxs-lookup"><span data-stu-id="0d0b8-102">How to: Enumerate Installed Fonts</span></span>
<span data-ttu-id="0d0b8-103"><xref:System.Drawing.Text.InstalledFontCollection>クラスから継承、<xref:System.Drawing.Text.FontCollection>抽象基本クラス。</span><span class="sxs-lookup"><span data-stu-id="0d0b8-103">The <xref:System.Drawing.Text.InstalledFontCollection> class inherits from the <xref:System.Drawing.Text.FontCollection> abstract base class.</span></span> <span data-ttu-id="0d0b8-104">使用することができます、<xref:System.Drawing.Text.InstalledFontCollection>コンピューターにインストールされているフォントを列挙するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0d0b8-104">You can use an <xref:System.Drawing.Text.InstalledFontCollection> object to enumerate the fonts installed on the computer.</span></span> <span data-ttu-id="0d0b8-105"><xref:System.Drawing.Text.FontCollection.Families%2A>のプロパティ、<xref:System.Drawing.Text.InstalledFontCollection>オブジェクトの配列は、<xref:System.Drawing.FontFamily>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0d0b8-105">The <xref:System.Drawing.Text.FontCollection.Families%2A> property of an <xref:System.Drawing.Text.InstalledFontCollection> object is an array of <xref:System.Drawing.FontFamily> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d0b8-106">例</span><span class="sxs-lookup"><span data-stu-id="0d0b8-106">Example</span></span>  
 <span data-ttu-id="0d0b8-107">次の例では、コンピューターにインストールされているすべてのフォント ファミリの名前が一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="0d0b8-107">The following example lists the names of all the font families installed on the computer.</span></span> <span data-ttu-id="0d0b8-108">コードを取得、<xref:System.Drawing.FontFamily.Name%2A>の各プロパティ<xref:System.Drawing.FontFamily>によって返される配列内のオブジェクト、<xref:System.Drawing.Text.FontCollection.Families%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="0d0b8-108">The code retrieves the <xref:System.Drawing.FontFamily.Name%2A> property of each <xref:System.Drawing.FontFamily> object in the array returned by the <xref:System.Drawing.Text.FontCollection.Families%2A> property.</span></span> <span data-ttu-id="0d0b8-109">ファミリ名を取得するには、フォームのコンマ区切りの一覧に連結されます。</span><span class="sxs-lookup"><span data-stu-id="0d0b8-109">As the family names are retrieved, they are concatenated to form a comma-separated list.</span></span> <span data-ttu-id="0d0b8-110">次に、<xref:System.Drawing.Graphics.DrawString%2A>のメソッド、<xref:System.Drawing.Graphics>クラスは、四角形で、コンマ区切りの一覧を描画します。</span><span class="sxs-lookup"><span data-stu-id="0d0b8-110">Then the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class draws the comma-separated list in a rectangle.</span></span>  
  
 <span data-ttu-id="0d0b8-111">コード例を実行する場合に、次の図に示すような出力になります。</span><span class="sxs-lookup"><span data-stu-id="0d0b8-111">If you run the example code, the output will be similar to that shown in the following illustration:</span></span>  
  
 ![インストールされているフォント ファミリを示すスクリーン ショット。](./media/how-to-enumerate-installed-fonts/list-installed-font-families.png)  
  
 [!code-csharp[System.Drawing.FontsAndText#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.FontsAndText#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0d0b8-113">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="0d0b8-113">Compiling the Code</span></span>  
 <span data-ttu-id="0d0b8-114">前の例は、Windows フォームで使用するために設計されています。 また必要が<xref:System.Windows.Forms.PaintEventArgs> `e`、はのパラメーター<xref:System.Windows.Forms.PaintEventHandler>します。</span><span class="sxs-lookup"><span data-stu-id="0d0b8-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span> <span data-ttu-id="0d0b8-115">さらに、インポートする必要があります、<xref:System.Drawing.Text>名前空間。</span><span class="sxs-lookup"><span data-stu-id="0d0b8-115">In addition, you should import the <xref:System.Drawing.Text> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d0b8-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d0b8-116">See also</span></span>

- [<span data-ttu-id="0d0b8-117">フォントとテキストの使用</span><span class="sxs-lookup"><span data-stu-id="0d0b8-117">Using Fonts and Text</span></span>](using-fonts-and-text.md)
