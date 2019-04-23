---
ms.openlocfilehash: 668d047d3247d64cb1400d4a9ea6887795fa0d44
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804399"
---
### <a name="httprequestcontentencoding-property-prohibits-utf7"></a><span data-ttu-id="dbfcc-101">HttpRequest.ContentEncoding プロパティで UTF7 が禁止される</span><span class="sxs-lookup"><span data-stu-id="dbfcc-101">HttpRequest.ContentEncoding property prohibits UTF7</span></span>

|   |   |
|---|---|
|<span data-ttu-id="dbfcc-102">説明</span><span class="sxs-lookup"><span data-stu-id="dbfcc-102">Details</span></span>|<span data-ttu-id="dbfcc-103">.NET Framework 4.5 以降では、<xref:System.Web.HttpRequest?displayProperty=name> の本文では UTF-7 エンコードが禁止されます。</span><span class="sxs-lookup"><span data-stu-id="dbfcc-103">Beginning in .NET Framework 4.5, UTF-7 encoding is prohibited in <xref:System.Web.HttpRequest?displayProperty=name>s' bodies.</span></span> <span data-ttu-id="dbfcc-104">UTF-7 データの受信を必要とするアプリケーションのデータが、正しくデコードされない場合があります。</span><span class="sxs-lookup"><span data-stu-id="dbfcc-104">Data for applications that depend on incoming UTF-7 data will not decode properly in some cases.</span></span>|
|<span data-ttu-id="dbfcc-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="dbfcc-105">Suggestion</span></span>|<span data-ttu-id="dbfcc-106">理想的には、<xref:System.Web.HttpRequest?displayProperty=name> で UTF-7 エンコードを使用しないようにアプリケーションを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbfcc-106">Ideally, applications should be updated to not use UTF-7 encoding in <xref:System.Web.HttpRequest?displayProperty=name>s.</span></span> <span data-ttu-id="dbfcc-107">または、 [<appSettings>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) 要素の <code>aspnet:AllowUtf7RequestContentEncoding</code> 属性を使用して、レガシ動作に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="dbfcc-107">Alternatively, legacy behavior can be restored by using the <code>aspnet:AllowUtf7RequestContentEncoding</code> attribute of the [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) element.</span></span>|
|<span data-ttu-id="dbfcc-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="dbfcc-108">Scope</span></span>|<span data-ttu-id="dbfcc-109">エッジ</span><span class="sxs-lookup"><span data-stu-id="dbfcc-109">Edge</span></span>|
|<span data-ttu-id="dbfcc-110">Version</span><span class="sxs-lookup"><span data-stu-id="dbfcc-110">Version</span></span>|<span data-ttu-id="dbfcc-111">4.5</span><span class="sxs-lookup"><span data-stu-id="dbfcc-111">4.5</span></span>|
|<span data-ttu-id="dbfcc-112">型</span><span class="sxs-lookup"><span data-stu-id="dbfcc-112">Type</span></span>|<span data-ttu-id="dbfcc-113">ランタイム</span><span class="sxs-lookup"><span data-stu-id="dbfcc-113">Runtime</span></span>|
|<span data-ttu-id="dbfcc-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="dbfcc-114">Affected APIs</span></span>|<ul><li><xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType></li></ul>|
