---
ms.openlocfilehash: f980c8029375074889505a8eb7e8a65aaa8d74e4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614769"
---
### <a name="resgen-refuses-to-load-content-from-the-web"></a><span data-ttu-id="0eac7-101">resgen で Web からのコンテンツの読み込みが拒否される</span><span class="sxs-lookup"><span data-stu-id="0eac7-101">Resgen refuses to load content from the web</span></span>

#### <a name="details"></a><span data-ttu-id="0eac7-102">説明</span><span class="sxs-lookup"><span data-stu-id="0eac7-102">Details</span></span>

<span data-ttu-id="0eac7-103">.resx ファイルには、バイナリ形式の入力が含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="0eac7-103">.resx files may contain binary formatted input.</span></span> <span data-ttu-id="0eac7-104">resgen を使用して、信頼されていない場所からダウンロードされたファイルを読み込もうとすると、既定で入力の読み込みに失敗します。</span><span class="sxs-lookup"><span data-stu-id="0eac7-104">If you attempt to use resgen to load a file that was downloaded from an untrusted location, it will fail to load the input by default.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0eac7-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="0eac7-105">Suggestion</span></span>

<span data-ttu-id="0eac7-106">信頼されていない場所からのバイナリ形式の入力を読み込む必要がある resgen ユーザーは、入力ファイルから Web のマークを削除するか、オプトアウト特性を適用できます。次のレジストリ設定を追加して、マシン全体のオプトアウト特性を適用します: [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft.NETFramework\SDK] &quot;AllowProcessOfUntrustedResourceFiles&quot;=&quot;true&quot;</span><span class="sxs-lookup"><span data-stu-id="0eac7-106">Resgen users who require loading binary formatted input from untrusted locations can either remove the mark of the web from the input file or apply the opt-out quirk.Add the following registry setting to apply the machine wide opt-out quirk: [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft.NETFramework\SDK] &quot;AllowProcessOfUntrustedResourceFiles&quot;=&quot;true&quot;</span></span>

| <span data-ttu-id="0eac7-107">名前</span><span class="sxs-lookup"><span data-stu-id="0eac7-107">Name</span></span>    | <span data-ttu-id="0eac7-108">[値]</span><span class="sxs-lookup"><span data-stu-id="0eac7-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0eac7-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="0eac7-109">Scope</span></span>   | <span data-ttu-id="0eac7-110">エッジ</span><span class="sxs-lookup"><span data-stu-id="0eac7-110">Edge</span></span>        |
| <span data-ttu-id="0eac7-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="0eac7-111">Version</span></span> | <span data-ttu-id="0eac7-112">4.7.2</span><span class="sxs-lookup"><span data-stu-id="0eac7-112">4.7.2</span></span>       |
| <span data-ttu-id="0eac7-113">種類</span><span class="sxs-lookup"><span data-stu-id="0eac7-113">Type</span></span>    | <span data-ttu-id="0eac7-114">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="0eac7-114">Retargeting</span></span> |
