---
title: プロジェクトで、XML スキーマのコンパイル中にエラーが発生しました
ms.date: 07/20/2015
f1_keywords:
- bc36810
- vbc36810
helpviewer_keywords:
- BC36810
ms.assetid: 9323b5d2-ba14-4e49-91f1-9ad647162144
ms.openlocfilehash: 7c05c712bcbb0a61bb3121bb71a7823a1c29afb5
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625583"
---
# <a name="errors-occurred-while-compiling-the-xml-schemas-in-the-project"></a><span data-ttu-id="bcd10-102">プロジェクトで、XML スキーマのコンパイル中にエラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="bcd10-102">Errors occurred while compiling the XML schemas in the project</span></span>
<span data-ttu-id="bcd10-103">プロジェクトでは、XML スキーマのコンパイル中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="bcd10-103">Errors occurred while compiling the XML schemas in the project.</span></span> <span data-ttu-id="bcd10-104">このため、XML IntelliSense は使用できません。</span><span class="sxs-lookup"><span data-stu-id="bcd10-104">Because of this, XML IntelliSense is not available.</span></span>  
  
 <span data-ttu-id="bcd10-105">プロジェクトに含まれる XML スキーマ定義 (XSD) スキーマでエラーがあります。</span><span class="sxs-lookup"><span data-stu-id="bcd10-105">There is an error in an XML Schema Definition (XSD) schema included in the project.</span></span> <span data-ttu-id="bcd10-106">このエラーは、既存の XSD スキーマとの競合がプロジェクトに設定する XSD スキーマ (.xsd) ファイルを追加するときに発生します。</span><span class="sxs-lookup"><span data-stu-id="bcd10-106">This error occurs when you add an XSD schema (.xsd) file that conflicts with the existing XSD schema set for the project.</span></span>  
  
 <span data-ttu-id="bcd10-107">**エラー ID:** BC36810</span><span class="sxs-lookup"><span data-stu-id="bcd10-107">**Error ID:** BC36810</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bcd10-108">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="bcd10-108">To correct this error</span></span>  
  
- <span data-ttu-id="bcd10-109">警告をダブルクリック、**エラー リスト**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="bcd10-109">Double-click the warning in the **Errors List** window.</span></span> <span data-ttu-id="bcd10-110">Visual Basic では、警告のソースである XSD ファイルの場所を実行します。</span><span class="sxs-lookup"><span data-stu-id="bcd10-110">Visual Basic will take you to the location in the XSD file that is the source of the warning.</span></span> <span data-ttu-id="bcd10-111">XSD スキーマでエラーを修正します。</span><span class="sxs-lookup"><span data-stu-id="bcd10-111">Correct the error in the XSD schema.</span></span>  
  
- <span data-ttu-id="bcd10-112">必要なすべての XSD スキーマ (.xsd) ファイルがプロジェクトに含まれることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bcd10-112">Ensure that all required XSD schema (.xsd) files are included in the project.</span></span> <span data-ttu-id="bcd10-113">をクリックする必要があります**すべてのファイル**上、**プロジェクト**メニュー、.xsd ファイル**ソリューション エクスプ ローラー**。</span><span class="sxs-lookup"><span data-stu-id="bcd10-113">You may need to click **Show All Files** on the **Project** menu to see your .xsd files in **Solution Explorer**.</span></span> <span data-ttu-id="bcd10-114">.Xsd ファイルを右クリックし、をクリックし、**プロジェクトに含める**ファイルをプロジェクトに含める。</span><span class="sxs-lookup"><span data-stu-id="bcd10-114">Right-click an .xsd file and then click **Include In Project** to include the file in your project.</span></span>  
  
- <span data-ttu-id="bcd10-115">XML to Schema ウィザードを使用している場合、同じソースから 1 回以上のスキーマを推論する場合にこのエラーが発生することができます。</span><span class="sxs-lookup"><span data-stu-id="bcd10-115">If you are using the XML to Schema Wizard, this error can occur if you infer schemas more than one time from the same source.</span></span> <span data-ttu-id="bcd10-116">スキーマ項目のテンプレートに新しい XML がこの場合、既存の XSD スキーマ ファイルを削除するには、プロジェクトから追加し、提供して XML to Schema ウィザード適用可能なすべての XML ソース プロジェクトの。</span><span class="sxs-lookup"><span data-stu-id="bcd10-116">In this case, you can remove the existing XSD schema files from the project, add a new XML to Schema item template, and then provide the XML to Schema Wizard with all the applicable XML sources for your project.</span></span>  
  
- <span data-ttu-id="bcd10-117">XSD スキーマのエラーが識別されない場合、XML コンパイラに詳細なエラー メッセージを提供するための十分な情報ことはできません。</span><span class="sxs-lookup"><span data-stu-id="bcd10-117">If no error is identified in your XSD schema, the XML compiler may not have enough information to provide a detailed error message.</span></span> <span data-ttu-id="bcd10-118">場合に、プロジェクトの一致に含まれる .xsd ファイルの XML 名前空間が、Visual Studio で設定する XML スキーマで特定された XML 名前空間を使用することを確認するより詳細なエラー情報を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="bcd10-118">You may be able to get more detailed error information if you ensure that the XML namespaces for the .xsd files included in your project match the XML namespaces identified for the XML Schema set in Visual Studio.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcd10-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="bcd10-119">See also</span></span>

- <span data-ttu-id="bcd10-120">[[エラー一覧] ウィンドウ](/visualstudio/ide/reference/error-list-window)</span><span class="sxs-lookup"><span data-stu-id="bcd10-120">[Error List Window](/visualstudio/ide/reference/error-list-window)</span></span>
- [<span data-ttu-id="bcd10-121">XML</span><span class="sxs-lookup"><span data-stu-id="bcd10-121">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)
