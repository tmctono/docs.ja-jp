---
ms.openlocfilehash: 5844dbc2c3c89baeb39b69f16846f92ac10e97f1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804595"
---
### <a name="xsd-schema-validation-now-correctly-detects-violations-of-unique-constraints-if-compound-keys-are-used-and-one-key-is-empty"></a><span data-ttu-id="28047-101">XSD スキーマ検証は、複合キーが使用され、1 つのキーが空の場合に、一意制約の違反を正しく検出するようになりました</span><span class="sxs-lookup"><span data-stu-id="28047-101">XSD Schema validation now correctly detects violations of unique constraints if compound keys are used and one key is empty</span></span>

|   |   |
|---|---|
|<span data-ttu-id="28047-102">説明</span><span class="sxs-lookup"><span data-stu-id="28047-102">Details</span></span>|<span data-ttu-id="28047-103">.NET Framework 4.6 より前のバージョンには、キーの 1 つが空であった場合、XSD 検証で複合キーの一意制約が検出されないというバグがありました。</span><span class="sxs-lookup"><span data-stu-id="28047-103">Versions of the .NET Framework prior to 4.6 had a bug that caused XSD validation to not detect unique constraints on compound keys if one of the keys was empty.</span></span> <span data-ttu-id="28047-104">.NET Framework 4.6 で、この問題は修正されました。</span><span class="sxs-lookup"><span data-stu-id="28047-104">In the .NET Framework 4.6, this issue is corrected.</span></span> <span data-ttu-id="28047-105">このため、より正しい検証が行われるようになりますが、以前は検証されていた XML の一部が検証されない可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="28047-105">This will result in more correct validation, but it may also result in some XML not validating which previously would have.</span></span>|
|<span data-ttu-id="28047-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="28047-106">Suggestion</span></span>|<span data-ttu-id="28047-107">より緩やかな .NET Framework 4.0 の検証が必要な場合、検証アプリケーションはバージョン 4.5 (またはそれ以前) の .NET Framework をターゲットにできます。</span><span class="sxs-lookup"><span data-stu-id="28047-107">If looser .NET Framework 4.0 validation is needed, the validating application can target version 4.5 (or earlier) of the .NET Framework.</span></span> <span data-ttu-id="28047-108">ただし、.NET Framework 4.6 に再ターゲットするときには、コード レビューを行って、重複する複合キー (この問題の説明で述べられているように) の検証を予期していないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28047-108">When retargeting to .NET Framework 4.6, however, code review should be done to be sure that duplicate compound keys (as described in this issue's description) are not expected to validate.</span></span>|
|<span data-ttu-id="28047-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="28047-109">Scope</span></span>|<span data-ttu-id="28047-110">エッジ</span><span class="sxs-lookup"><span data-stu-id="28047-110">Edge</span></span>|
|<span data-ttu-id="28047-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="28047-111">Version</span></span>|<span data-ttu-id="28047-112">4.6</span><span class="sxs-lookup"><span data-stu-id="28047-112">4.6</span></span>|
|<span data-ttu-id="28047-113">[種類]</span><span class="sxs-lookup"><span data-stu-id="28047-113">Type</span></span>|<span data-ttu-id="28047-114">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="28047-114">Retargeting</span></span>|
