---
ms.openlocfilehash: ad953a1562db407c04d7860c60eb5964fe6fe2ca
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620345"
---
### <a name="deserialization-of-mailmessage-objects-serialized-under-the-net-framework-45-may-fail"></a><span data-ttu-id="768a4-101">.NET Framework 4.5 でシリアル化された MailMessage オブジェクトの逆シリアル化が失敗する可能性がある</span><span class="sxs-lookup"><span data-stu-id="768a4-101">Deserialization of MailMessage objects serialized under the .NET Framework 4.5 may fail</span></span>

#### <a name="details"></a><span data-ttu-id="768a4-102">説明</span><span class="sxs-lookup"><span data-stu-id="768a4-102">Details</span></span>

<span data-ttu-id="768a4-103">.NET Framework 4.5 以降では、<xref:System.Web.Mail.MailMessage> オブジェクトに非 ASCII 文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="768a4-103">Starting with the .NET Framework 4.5, <xref:System.Web.Mail.MailMessage> objects can include non-ASCII characters.</span></span> <span data-ttu-id="768a4-104">.NET Framework 4 では、ASCII 文字しかサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="768a4-104">In the .NET Framework 4, only ASCII characters are supported.</span></span> <span data-ttu-id="768a4-105">非 ASCII 文字が含まれ、.NET Framework 4.5 以降でシリアル化された <xref:System.Web.Mail.MailMessage> オブジェクトは、.NET Framework 4 で逆シリアル化することはできません。</span><span class="sxs-lookup"><span data-stu-id="768a4-105"><xref:System.Web.Mail.MailMessage> objects that contain non-ASCII characters and that are serialized under the .NET Framework 4.5 or later cannot be deserialized under the .NET Framework 4.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="768a4-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="768a4-106">Suggestion</span></span>

<span data-ttu-id="768a4-107"><xref:System.Web.Mail.MailMessage> オブジェクトの逆シリアル化時に、コードで例外処理が提供されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="768a4-107">Ensure that your code provides exception handling when deserializing a <xref:System.Web.Mail.MailMessage> object.</span></span>

| <span data-ttu-id="768a4-108">名前</span><span class="sxs-lookup"><span data-stu-id="768a4-108">Name</span></span>    | <span data-ttu-id="768a4-109">[値]</span><span class="sxs-lookup"><span data-stu-id="768a4-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="768a4-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="768a4-110">Scope</span></span>   |<span data-ttu-id="768a4-111">マイナー</span><span class="sxs-lookup"><span data-stu-id="768a4-111">Minor</span></span>|
|<span data-ttu-id="768a4-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="768a4-112">Version</span></span>|<span data-ttu-id="768a4-113">4.5</span><span class="sxs-lookup"><span data-stu-id="768a4-113">4.5</span></span>|
|<span data-ttu-id="768a4-114">種類</span><span class="sxs-lookup"><span data-stu-id="768a4-114">Type</span></span>|<span data-ttu-id="768a4-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="768a4-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="768a4-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="768a4-116">Affected APIs</span></span>

-<xref:System.Web.Mail.MailMessage?displayProperty=nameWithType></li></ul>|
