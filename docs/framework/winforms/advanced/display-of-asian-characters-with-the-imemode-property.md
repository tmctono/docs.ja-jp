---
title: ImeMode プロパティによるアジア言語の文字表示
ms.date: 03/30/2017
helpviewer_keywords:
- Asian languages [Windows Forms], displaying with ImeMode
- Chinese characters [Windows Forms], displaying with ImeMode
- IME mode
- Japanese characters [Windows Forms], displaying with ImeMode
- international applications [Windows Forms], character display
- international characters
- Korean characters
- Asian languages
- Input Method Editor (IME), mode
- localization [Windows Forms], character sets
- globalization [Windows Forms], character sets
ms.assetid: c60ae399-0dab-4f07-9dea-6dbfb15ec0ae
ms.openlocfilehash: 25602e1a878443bd54411dfd6481581abebda5c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755481"
---
# <a name="display-of-asian-characters-with-the-imemode-property"></a><span data-ttu-id="e3ee2-102">ImeMode プロパティによるアジア言語の文字表示</span><span class="sxs-lookup"><span data-stu-id="e3ee2-102">Display of Asian Characters with the ImeMode Property</span></span>
<span data-ttu-id="e3ee2-103"><xref:System.Windows.Forms.Control.ImeMode%2A>プロパティは、入力方式エディター (IME) の特定のモードを強制するフォームとコントロールによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="e3ee2-103">The <xref:System.Windows.Forms.Control.ImeMode%2A> property is used by forms and controls to force a specific mode for an input method editor (IME).</span></span> <span data-ttu-id="e3ee2-104">IME は、日本語、中国語、韓国語のスクリプトを記述するために不可欠なコンポーネントです。これらの記述システムには、通常のキーボードではエンコードできない多くの文字があります。</span><span class="sxs-lookup"><span data-stu-id="e3ee2-104">The IME is an essential component for writing Chinese, Japanese, and Korean scripts, since these writing systems have more characters than can be encoded for a regular keyboard.</span></span> <span data-ttu-id="e3ee2-105">たとえば、特定のテキスト ボックスで ASCII 文字のみを許可したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="e3ee2-105">For example, you may want to allow only ASCII characters in a particular text box.</span></span> <span data-ttu-id="e3ee2-106">このようなケースで設定できます、<xref:System.Windows.Forms.Control.ImeMode%2A>プロパティを<xref:System.Windows.Forms.ImeMode>ユーザーはその特定のテキスト ボックスに ASCII 文字を入力できるとします。</span><span class="sxs-lookup"><span data-stu-id="e3ee2-106">In such a case you can set the <xref:System.Windows.Forms.Control.ImeMode%2A> property to <xref:System.Windows.Forms.ImeMode> and users will only be able to enter ASCII characters for that particular text box.</span></span> <span data-ttu-id="e3ee2-107">既定値、<xref:System.Windows.Forms.Control.ImeMode%2A>プロパティは<xref:System.Windows.Forms.ImeMode>ので、フォームのプロパティを設定すると、フォーム上のすべてのコントロールはその設定を継承します。</span><span class="sxs-lookup"><span data-stu-id="e3ee2-107">The default value of the <xref:System.Windows.Forms.Control.ImeMode%2A> property is <xref:System.Windows.Forms.ImeMode>, so if you set the property for a form, all controls on the form will inherit that setting.</span></span> <span data-ttu-id="e3ee2-108">詳細については、次を参照してください。 <xref:System.Windows.Forms.Control.ImeMode%2A> ) と<xref:System.Windows.Forms.ImeMode>します。</span><span class="sxs-lookup"><span data-stu-id="e3ee2-108">For more information, see <xref:System.Windows.Forms.Control.ImeMode%2A> ) and <xref:System.Windows.Forms.ImeMode>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3ee2-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="e3ee2-109">See also</span></span>

- [<span data-ttu-id="e3ee2-110">Windows フォーム アプリケーションのグローバル化</span><span class="sxs-lookup"><span data-stu-id="e3ee2-110">Globalizing Windows Forms applications</span></span>](globalizing-windows-forms.md)
