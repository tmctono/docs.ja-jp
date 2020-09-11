---
ms.openlocfilehash: 7140f6d4cac063088b3663ab98d292104218b542
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465515"
---
### <a name="cookie-path-handling-now-conforms-to-rfc-6265"></a><span data-ttu-id="8039c-101">現在、Cookie パスの処理は、RFC 6265 に準拠している</span><span class="sxs-lookup"><span data-stu-id="8039c-101">Cookie Path handling now conforms to RFC 6265</span></span>

<span data-ttu-id="8039c-102"><xref:System.Net.Cookie> クラスと <xref:System.Net.CookieContainer> クラスについては、[RFC 6265](https://tools.ietf.org/html/rfc6265) に定義されているパス処理アルゴリズムが実装されました。</span><span class="sxs-lookup"><span data-stu-id="8039c-102">Path-handling algorithms defined in [RFC 6265](https://tools.ietf.org/html/rfc6265) were implemented for the <xref:System.Net.Cookie> and <xref:System.Net.CookieContainer> classes.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="8039c-103">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="8039c-103">Version introduced</span></span>

<span data-ttu-id="8039c-104">5.0</span><span class="sxs-lookup"><span data-stu-id="8039c-104">5.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="8039c-105">変更の説明</span><span class="sxs-lookup"><span data-stu-id="8039c-105">Change description</span></span>

- <span data-ttu-id="8039c-106"><xref:System.Net.Cookie.Path> プロパティは、要求パスのプレフィックスにする必要がなくなりました。</span><span class="sxs-lookup"><span data-stu-id="8039c-106">The <xref:System.Net.Cookie.Path> property is no longer required to be a prefix of the request path.</span></span>
- <span data-ttu-id="8039c-107">RFC 6265 の[セクション 5.1.4](https://tools.ietf.org/html/rfc6265#section-5.1.4) に定義されているように、<xref:System.Net.Cookie.Path> の既定値の計算とパス照合アルゴリズムが導入されました。</span><span class="sxs-lookup"><span data-stu-id="8039c-107">The calculation of the default value of <xref:System.Net.Cookie.Path> and path-matching algorithms were implemented as defined in [section 5.1.4](https://tools.ietf.org/html/rfc6265#section-5.1.4) of RFC 6265.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="8039c-108">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="8039c-108">Recommended action</span></span>

<span data-ttu-id="8039c-109">ほとんどの場合、お客様が何らかのアクションを実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8039c-109">In most cases, you won't need to take any action.</span></span> <span data-ttu-id="8039c-110">ただし、コードが <xref:System.Net.Cookie.Path> 検証に依存していた場合、必要な検証をコードに実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8039c-110">However, if your code was dependent on <xref:System.Net.Cookie.Path> validation, you'll need to implement required validation in your code.</span></span> <span data-ttu-id="8039c-111">コードが <xref:System.Net.Cookie.Path> の既定値計算に依存している場合、既定値を使用せず、手動で <xref:System.Net.Cookie.Path> 値を指定することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="8039c-111">If your code was dependent on default value calculation for <xref:System.Net.Cookie.Path>, consider supplying the <xref:System.Net.Cookie.Path> value manually instead of using the default value.</span></span>

#### <a name="category"></a><span data-ttu-id="8039c-112">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="8039c-112">Category</span></span>

<span data-ttu-id="8039c-113">ネットワーキング</span><span class="sxs-lookup"><span data-stu-id="8039c-113">Networking</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="8039c-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="8039c-114">Affected APIs</span></span>

- <xref:System.Net.Cookie?displayProperty=fullName>
- <xref:System.Net.CookieContainer?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Net.Cookie`
- `T:System.Net.CookieContainer`

-->
