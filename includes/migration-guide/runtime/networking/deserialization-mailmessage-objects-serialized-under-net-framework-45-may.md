---
ms.openlocfilehash: a6f93bbdf39a1b525e2daeb12afc3a6392a66e30
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59235753"
---
### <a name="deserialization-of-mailmessage-objects-serialized-under-the-net-framework-45-may-fail"></a><span data-ttu-id="fa402-101">.NET Framework 4.5 でシリアル化された MailMessage オブジェクトの逆シリアル化が失敗する可能性がある</span><span class="sxs-lookup"><span data-stu-id="fa402-101">Deserialization of MailMessage objects serialized under the .NET Framework 4.5 may fail</span></span>

|   |   |
|---|---|
|<span data-ttu-id="fa402-102">説明</span><span class="sxs-lookup"><span data-stu-id="fa402-102">Details</span></span>|<span data-ttu-id="fa402-103">.NET Framework 4.5 以降では、<xref:System.Web.Mail.MailMessage> オブジェクトに非 ASCII 文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="fa402-103">Starting with the .NET Framework 4.5, <xref:System.Web.Mail.MailMessage> objects can include non-ASCII characters.</span></span> <span data-ttu-id="fa402-104">.NET Framework 4 では、ASCII 文字しかサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="fa402-104">In the .NET Framework 4, only ASCII characters are supported.</span></span> <span data-ttu-id="fa402-105">非 ASCII 文字が含まれ、.NET Framework 4.5 以降でシリアル化された <xref:System.Web.Mail.MailMessage> オブジェクトは、.NET Framework 4 で逆シリアル化することはできません。</span><span class="sxs-lookup"><span data-stu-id="fa402-105"><xref:System.Web.Mail.MailMessage> objects that contain non-ASCII characters and that are serialized under the .NET Framework 4.5 or later cannot be deserialized under the .NET Framework 4.</span></span>|
|<span data-ttu-id="fa402-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="fa402-106">Suggestion</span></span>|<span data-ttu-id="fa402-107"><xref:System.Web.Mail.MailMessage> オブジェクトの逆シリアル化時に、コードで例外処理が提供されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fa402-107">Ensure that your code provides exception handling when deserializing a <xref:System.Web.Mail.MailMessage> object.</span></span>|
|<span data-ttu-id="fa402-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="fa402-108">Scope</span></span>|<span data-ttu-id="fa402-109">マイナー</span><span class="sxs-lookup"><span data-stu-id="fa402-109">Minor</span></span>|
|<span data-ttu-id="fa402-110">Version</span><span class="sxs-lookup"><span data-stu-id="fa402-110">Version</span></span>|<span data-ttu-id="fa402-111">4.5</span><span class="sxs-lookup"><span data-stu-id="fa402-111">4.5</span></span>|
|<span data-ttu-id="fa402-112">型</span><span class="sxs-lookup"><span data-stu-id="fa402-112">Type</span></span>|<span data-ttu-id="fa402-113">ランタイム</span><span class="sxs-lookup"><span data-stu-id="fa402-113">Runtime</span></span>|
|<span data-ttu-id="fa402-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="fa402-114">Affected APIs</span></span>|<ul><li><xref:System.Web.Mail.MailMessage?displayProperty=nameWithType></li></ul>|
