---
title: 遅延バインドの解決です。ランタイム エラーが発生する可能性があります。
ms.date: 07/20/2015
f1_keywords:
- vbc42017
- BC42017
helpviewer_keywords:
- BC42017
ms.assetid: 45f552c8-57c6-44c0-97d3-e510119b257a
ms.openlocfilehash: 6b78dfed1d615ba865f136365eac1c9c131ed5a5
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64661948"
---
# <a name="late-bound-resolution-runtime-errors-could-occur"></a><span data-ttu-id="1d62e-102">遅延バインドの解決です。ランタイム エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1d62e-102">Late bound resolution; runtime errors could occur</span></span>
<span data-ttu-id="1d62e-103">オブジェクトが宣言する変数に割り当てられている、 [Object データ型](../../../visual-basic/language-reference/data-types/object-data-type.md)します。</span><span class="sxs-lookup"><span data-stu-id="1d62e-103">An object is assigned to a variable declared to be of the [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="1d62e-104">として変数を宣言するときに`Object`、コンパイラを実行する必要があります*遅延バインディング*、実行時に余分な処理を停止します。</span><span class="sxs-lookup"><span data-stu-id="1d62e-104">When you declare a variable as `Object`, the compiler must perform *late binding*, which causes extra operations at run time.</span></span> <span data-ttu-id="1d62e-105">また、アプリケーションで実行時エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1d62e-105">It also exposes your application to potential run-time errors.</span></span> <span data-ttu-id="1d62e-106">割り当てる場合など、<xref:System.Windows.Forms.Form>を`Object`変数にアクセスしようと、<xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=nameWithType>プロパティ、ランタイムは、スロー、<xref:System.MemberAccessException>ため、<xref:System.Windows.Forms.Form>クラスを公開しません、`NameTable`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="1d62e-106">For example, if you assign a <xref:System.Windows.Forms.Form> to the `Object` variable and then try to access the <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=nameWithType> property, the runtime throws a <xref:System.MemberAccessException> because the <xref:System.Windows.Forms.Form> class does not expose a `NameTable` property.</span></span>  
  
 <span data-ttu-id="1d62e-107">特定の型の変数を宣言する場合、コンパイラを実行できます*事前バインディング*コンパイル時にします。</span><span class="sxs-lookup"><span data-stu-id="1d62e-107">If you declare the variable to be of a specific type, the compiler can perform *early binding* at compile time.</span></span> <span data-ttu-id="1d62e-108">これは、結果、パフォーマンスの向上、特定の型のメンバーと、コードの読みやすさへのアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="1d62e-108">This results in improved performance, controlled access to the members of the specific type, and better readability of your code.</span></span>  
  
 <span data-ttu-id="1d62e-109">既定では、このメッセージは警告です。</span><span class="sxs-lookup"><span data-stu-id="1d62e-109">By default, this message is a warning.</span></span> <span data-ttu-id="1d62e-110">警告を非表示にする方法や、警告をエラーとして扱う方法の詳細については、「[Visual Basic での警告の構成](/visualstudio/ide/configuring-warnings-in-visual-basic)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1d62e-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="1d62e-111">**エラー ID:** BC42017</span><span class="sxs-lookup"><span data-stu-id="1d62e-111">**Error ID:** BC42017</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1d62e-112">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="1d62e-112">To correct this error</span></span>  
  
- <span data-ttu-id="1d62e-113">可能であれば、特定の型の変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="1d62e-113">If possible, declare the variable to be of a specific type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d62e-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="1d62e-114">See also</span></span>

- [<span data-ttu-id="1d62e-115">事前バインディングと遅延バインディング</span><span class="sxs-lookup"><span data-stu-id="1d62e-115">Early and Late Binding</span></span>](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
- [<span data-ttu-id="1d62e-116">オブジェクト変数の宣言</span><span class="sxs-lookup"><span data-stu-id="1d62e-116">Object Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
