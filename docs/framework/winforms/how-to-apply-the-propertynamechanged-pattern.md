---
title: '方法: PropertyNameChanged パターンを適用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- data binding [Windows Forms], custom controls
- PropertyNameChanged pattern [Windows Forms], applying
ms.assetid: aa47ddf6-5223-40c4-833f-a78992194836
ms.openlocfilehash: 01afa713e97206ea192ba55dc2affad20163f872
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665262"
---
# <a name="how-to-apply-the-propertynamechanged-pattern"></a><span data-ttu-id="83a92-102">方法: PropertyNameChanged パターンを適用する</span><span class="sxs-lookup"><span data-stu-id="83a92-102">How to: Apply the PropertyNameChanged Pattern</span></span>
<span data-ttu-id="83a92-103">次のコード例は、適用する方法を示します、 *PropertyName*Changed パターンをカスタム コントロール。</span><span class="sxs-lookup"><span data-stu-id="83a92-103">The following code example demonstrates how to apply the *PropertyName*Changed pattern to a custom control.</span></span> <span data-ttu-id="83a92-104">Windows フォーム データ バインディング エンジンで使用されるカスタム コントロールを実装する場合は、このパターンを適用します。</span><span class="sxs-lookup"><span data-stu-id="83a92-104">Apply this pattern when you implement custom controls that are used with the Windows Forms data binding engine.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83a92-105">例</span><span class="sxs-lookup"><span data-stu-id="83a92-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.ChangeNotification#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/CS/Form1.cs#3)]
 [!code-vb[System.Windows.Forms.ChangeNotification#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="83a92-106">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="83a92-106">Compiling the Code</span></span>  
 <span data-ttu-id="83a92-107">上記のコード例をコンパイルするには。</span><span class="sxs-lookup"><span data-stu-id="83a92-107">To compile the previous code example:</span></span>  
  
- <span data-ttu-id="83a92-108">空のコード ファイルには、コードを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="83a92-108">Paste the code into an empty code file.</span></span> <span data-ttu-id="83a92-109">含む Windows フォームでのカスタム コントロールを使用する必要があります、`Main`メソッド。</span><span class="sxs-lookup"><span data-stu-id="83a92-109">You must use the custom control on a Windows Form that contains a `Main` method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83a92-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="83a92-110">See also</span></span>

- [<span data-ttu-id="83a92-111">方法: INotifyPropertyChanged インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="83a92-111">How to: Implement the INotifyPropertyChanged Interface</span></span>](how-to-implement-the-inotifypropertychanged-interface.md)
- [<span data-ttu-id="83a92-112">Windows フォーム データ バインドの変更通知</span><span class="sxs-lookup"><span data-stu-id="83a92-112">Change Notification in Windows Forms Data Binding</span></span>](change-notification-in-windows-forms-data-binding.md)
- [<span data-ttu-id="83a92-113">Windows フォームでのデータ バインディング</span><span class="sxs-lookup"><span data-stu-id="83a92-113">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
