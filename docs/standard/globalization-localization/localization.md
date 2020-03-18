---
title: ローカリゼーション
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- culture, localization
- application development [.NET Framework], localization
- globalization [.NET Framework], localization
- code blocks
- international applications [.NET Framework], localization
- global applications, localization
- world-ready applications, localization
- user interface blocks
- localization [.NET Framework], about localization
- localizing resources
ms.assetid: 49d520d7-92d7-44ee-bb24-8b615db1d41b
ms.openlocfilehash: 89851c42570f301bee8a3eca744eb5d069347d4e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "73120869"
---
# <a name="localization"></a><span data-ttu-id="d03c4-102">ローカリゼーション</span><span class="sxs-lookup"><span data-stu-id="d03c4-102">Localization</span></span>

<span data-ttu-id="d03c4-103">ローカリゼーションはアプリケーションのリソースを翻訳するプロセスであり、そのアプリケーションで対応するカルチャ別のバージョンが作られます。</span><span class="sxs-lookup"><span data-stu-id="d03c4-103">Localization is the process of translating an application's resources into localized versions for each culture that the application will support.</span></span> <span data-ttu-id="d03c4-104">[ローカライズ化の確認](../../../docs/standard/globalization-localization/localizability-review.md)手順で世界展開するアプリケーションがローカライズ可能であることを確認してから、ローカリゼーション手順に進んでください。</span><span class="sxs-lookup"><span data-stu-id="d03c4-104">You should proceed to the localization step only after completing the [Localizability Review](../../../docs/standard/globalization-localization/localizability-review.md) step to verify that the globalized application is ready for localization.</span></span>

<span data-ttu-id="d03c4-105">ローカライズ可能なアプリケーションは、概念的に 2 つのブロックに分けられます。すべてのユーザー インターフェイス要素を含むブロックと実行可能なコードを含むブロックです。</span><span class="sxs-lookup"><span data-stu-id="d03c4-105">An application that is ready for localization is separated into two conceptual blocks: a block that contains all user interface elements and a block that contains executable code.</span></span> <span data-ttu-id="d03c4-106">ユーザー インターフェイス ブロックには、ローカライズ可能なユーザー インターフェイス要素のみが含まれます。ニュートラル カルチャの場合、文字列、エラー メッセージ、ダイアログ ボックス、メニュー、埋め込みオブジェクト リソースなどです。</span><span class="sxs-lookup"><span data-stu-id="d03c4-106">The user interface block contains only localizable user-interface elements such as strings, error messages, dialog boxes, menus, embedded object resources, and so on for the neutral culture.</span></span> <span data-ttu-id="d03c4-107">コード ブロックには、すべての対応カルチャで使用されるアプリケーション コードのみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d03c4-107">The code block contains only the application code to be used by all supported cultures.</span></span> <span data-ttu-id="d03c4-108">共通言語ランタイムは、アプリケーションの実行可能コードをそのリソースから分離させるサテライト アセンブリ リソース モデルに対応しています。</span><span class="sxs-lookup"><span data-stu-id="d03c4-108">The common language runtime supports a satellite assembly resource model that separates an application's executable code from its resources.</span></span> <span data-ttu-id="d03c4-109">このモデルの実装方法については、[.NET のリソース](../../../docs/framework/resources/index.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d03c4-109">For more information about implementing this model, see [Resources in .NET](../../../docs/framework/resources/index.md).</span></span>

<span data-ttu-id="d03c4-110">アプリケーションのローカライズ バージョンごとに、ターゲット カルチャの言語に翻訳されたユーザー インターフェイス ブロックを含む新しいサテライト アセンブリを追加します。</span><span class="sxs-lookup"><span data-stu-id="d03c4-110">For each localized version of your application, add a new satellite assembly that contains the localized user interface block translated into the appropriate language for the target culture.</span></span> <span data-ttu-id="d03c4-111">すべてのカルチャのコード ブロックを同じにしてください。</span><span class="sxs-lookup"><span data-stu-id="d03c4-111">The code block for all cultures should remain the same.</span></span> <span data-ttu-id="d03c4-112">ユーザー インターフェイス ブロックのローカライズされたバージョンとコード ブロックを組み合わせることで、アプリケーションのローカライズ バージョンが作られます。</span><span class="sxs-lookup"><span data-stu-id="d03c4-112">The combination of a localized version of the user interface block with the code block produces a localized version of your application.</span></span>

<span data-ttu-id="d03c4-113">Windows ソフトウェア開発キット (SDK) には Windows フォーム リソース エディター (Winres.exe) があります。このエディターでは、ターゲット カルチャに合わせて Windows フォームを簡単にローカライズできます。</span><span class="sxs-lookup"><span data-stu-id="d03c4-113">The Windows Software Development Kit (SDK) supplies the Windows Forms Resource Editor (Winres.exe) that allows you to quickly localize Windows Forms for target cultures.</span></span> <span data-ttu-id="d03c4-114">このツールの使用方法については、「[Winres.exe (Windows フォーム リソース エディター)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d03c4-114">For information about using this tool, see [Winres.exe (Windows Forms Resource Editor)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d03c4-115">参照</span><span class="sxs-lookup"><span data-stu-id="d03c4-115">See also</span></span>

- [<span data-ttu-id="d03c4-116">グローバライズとローカライズ</span><span class="sxs-lookup"><span data-stu-id="d03c4-116">Globalization and Localization</span></span>](../../../docs/standard/globalization-localization/index.md)
- [<span data-ttu-id="d03c4-117">ローカライズ化の確認</span><span class="sxs-lookup"><span data-stu-id="d03c4-117">Localizability Review</span></span>](../../../docs/standard/globalization-localization/localizability-review.md)
- [<span data-ttu-id="d03c4-118">グローバリゼーション</span><span class="sxs-lookup"><span data-stu-id="d03c4-118">Globalization</span></span>](../../../docs/standard/globalization-localization/globalization.md)
- [<span data-ttu-id="d03c4-119">デスクトップ アプリケーションのリソース</span><span class="sxs-lookup"><span data-stu-id="d03c4-119">Resources in Desktop Apps</span></span>](../../../docs/framework/resources/index.md)
