---
title: '方法: アクセス キーおよびテキスト折り返し機能を持つコントロールを作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- access keys [WPF], control for
- controls [WPF], text wrapping
- wrapping text [WPF]
- keys [WPF], control for
- controls [WPF], access keys
- text wrapping [WPF]
ms.assetid: 205099d9-2551-4302-a25e-a15af9f67e04
ms.openlocfilehash: 48e439719afa2426b5d8f822c621080cdc32514e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910924"
---
# <a name="how-to-create-a-control-that-has-an-access-key-and-text-wrapping"></a><span data-ttu-id="394c2-102">方法: アクセス キーおよびテキスト折り返し機能を持つコントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="394c2-102">How to: Create a Control That Has an Access Key and Text Wrapping</span></span>
<span data-ttu-id="394c2-103">この例では、アクセス キーがありテキスト折り返しをサポートするコントロールを作成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="394c2-103">This example shows how to create a control that has an access key and supports text wrapping.</span></span> <span data-ttu-id="394c2-104">この例では、<xref:System.Windows.Controls.Label> を使用してこれらの概念を図解します。</span><span class="sxs-lookup"><span data-stu-id="394c2-104">The example uses a <xref:System.Windows.Controls.Label> control to illustrate these concepts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="394c2-105">例</span><span class="sxs-lookup"><span data-stu-id="394c2-105">Example</span></span>  
 <span data-ttu-id="394c2-106">**ラベルにテキスト折り返し機能を追加する**</span><span class="sxs-lookup"><span data-stu-id="394c2-106">**Add Text Wrapping to Your Label**</span></span>  
  
 <span data-ttu-id="394c2-107"><xref:System.Windows.Controls.Label> コントロールはテキストの折り返しに対応していません。</span><span class="sxs-lookup"><span data-stu-id="394c2-107">The <xref:System.Windows.Controls.Label> control does not support text wrapping.</span></span> <span data-ttu-id="394c2-108">複数の行を折り返せるラベルが必要な場合には、テキスト折り返し機能をサポートしている別の要素を入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="394c2-108">If you need a label that wraps across multiple lines, you can nest another element that does support text wrapping and put the element inside the label.</span></span> <span data-ttu-id="394c2-109">次の例では、<xref:System.Windows.Controls.TextBlock> を使用して複数行のテキストを折り返せるラベルを作成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="394c2-109">The following example shows how to use a <xref:System.Windows.Controls.TextBlock> to make a label that wraps several lines of text.</span></span>  
  
 [!code-xaml[LabelSnippet#5](~/samples/snippets/csharp/VS_Snippets_Wpf/LabelSnippet/CS/Pane1.xaml#5)]  
  
 <span data-ttu-id="394c2-110">**アクセス キーおよびテキスト折り返し機能をラベルに追加する**</span><span class="sxs-lookup"><span data-stu-id="394c2-110">**Add an Access Key and Text Wrapping to Your Label**</span></span>  
  
 <span data-ttu-id="394c2-111">アクセスキー (ニーモニック) のある <xref:System.Windows.Controls.Label> が必要な場合、<xref:System.Windows.Controls.Label> 内にある <xref:System.Windows.Controls.AccessText> 要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="394c2-111">If you need a <xref:System.Windows.Controls.Label> that has an access key (mnemonic), use the <xref:System.Windows.Controls.AccessText> element that is inside the <xref:System.Windows.Controls.Label>.</span></span>  
  
 <span data-ttu-id="394c2-112"><xref:System.Windows.Controls.Label>、<xref:System.Windows.Controls.Button>、<xref:System.Windows.Controls.RadioButton>、<xref:System.Windows.Controls.CheckBox>、<xref:System.Windows.Controls.MenuItem>、<xref:System.Windows.Controls.TabItem>、<xref:System.Windows.Controls.Expander>、<xref:System.Windows.Controls.GroupBox> などのコントロールには、既定のコントロール テンプレートがあります。</span><span class="sxs-lookup"><span data-stu-id="394c2-112">Controls such as <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.RadioButton>, <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.Expander>, and <xref:System.Windows.Controls.GroupBox> have default control templates.</span></span> <span data-ttu-id="394c2-113">これらのテンプレートには <xref:System.Windows.Controls.ContentPresenter> が含まれています。</span><span class="sxs-lookup"><span data-stu-id="394c2-113">These templates contain a <xref:System.Windows.Controls.ContentPresenter>.</span></span> <span data-ttu-id="394c2-114"><xref:System.Windows.Controls.ContentPresenter> で設定できるプロパティの 1 つに <xref:System.Windows.Controls.ContentPresenter.RecognizesAccessKey%2A>="true" があります。これを利用し、コントロールのアクセス キーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="394c2-114">One of the properties that you can set on the <xref:System.Windows.Controls.ContentPresenter> is <xref:System.Windows.Controls.ContentPresenter.RecognizesAccessKey%2A>="true", which you can use to specify an access key for the control.</span></span>  
  
 <span data-ttu-id="394c2-115">次の例では、アクセス キーがあり、テキスト折り返しをサポートする <xref:System.Windows.Controls.Label> を作成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="394c2-115">The following example shows how to create a <xref:System.Windows.Controls.Label> that has an access key and supports text wrapping.</span></span> <span data-ttu-id="394c2-116">この例ではテキスト折り返し機能を有効にするために、<xref:System.Windows.Controls.AccessText.TextWrapping%2A> プロパティを設定し、下線文字を使用してアクセス キーを指定します。</span><span class="sxs-lookup"><span data-stu-id="394c2-116">To enable text wrapping, the example sets the <xref:System.Windows.Controls.AccessText.TextWrapping%2A> property and uses an underline character to specify the access key.</span></span> <span data-ttu-id="394c2-117">(下線文字の直後の文字はアクセス キーになります。)</span><span class="sxs-lookup"><span data-stu-id="394c2-117">(The character that immediately follows the underline character is the access key.)</span></span>  
  
 [!code-xaml[LabelSnippet#4](~/samples/snippets/csharp/VS_Snippets_Wpf/LabelSnippet/CS/Pane1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="394c2-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="394c2-118">See also</span></span>

- <span data-ttu-id="394c2-119">[方法: ラベルのターゲット プロパティを設定する](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752101(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="394c2-119">[How to: Set the Target Property of a Label](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752101(v=vs.90))</span></span>
