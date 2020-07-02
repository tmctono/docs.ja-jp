---
ms.openlocfilehash: 768a948849064cedb38110f5ed271717442325c0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620315"
---
### <a name="log-file-name-created-by-the-objectcontextcreatedatabase-method-has-changed-to-match-sql-server-specifications"></a><span data-ttu-id="585bd-101">ObjectContext.CreateDatabase メソッドによって作成されたログ ファイル名が、SQL Server の仕様に一致するように変更された</span><span class="sxs-lookup"><span data-stu-id="585bd-101">Log file name created by the ObjectContext.CreateDatabase method has changed to match SQL Server specifications</span></span>

#### <a name="details"></a><span data-ttu-id="585bd-102">説明</span><span class="sxs-lookup"><span data-stu-id="585bd-102">Details</span></span>

<span data-ttu-id="585bd-103"><xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=fullName> メソッドが、直接、または SqlClient プロバイダーと共に Code First と接続文字列の AttachDBFilename 値を使用して呼び出されると、filename.ldf (filename は AttachDBFilename 値によって指定されたファイルの名前) ではなく、filename_log.ldf という名前のログ ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="585bd-103">When the <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=fullName> method is called either directly or by using Code First with the SqlClient provider and an AttachDBFilename value in the connection string, it creates a log file named filename_log.ldf instead of filename.ldf (where filename is the name of the file specified by the AttachDBFilename value).</span></span> <span data-ttu-id="585bd-104">この変更により、SQL Server の仕様に従ってログ ファイル名が提供されるため、デバッグ機能が向上します。</span><span class="sxs-lookup"><span data-stu-id="585bd-104">This change improves debugging by providing a log file named according to SQL Server specifications.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="585bd-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="585bd-105">Suggestion</span></span>

<span data-ttu-id="585bd-106">ログ ファイル名がアプリケーションにとって重要な場合、標準の _log.ldf ファイル名形式を予期するように、アプリケーションを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="585bd-106">If the log file name is important for an app, the app should be updated to expect the standard _log.ldf file name format.</span></span>

| <span data-ttu-id="585bd-107">名前</span><span class="sxs-lookup"><span data-stu-id="585bd-107">Name</span></span>    | <span data-ttu-id="585bd-108">[値]</span><span class="sxs-lookup"><span data-stu-id="585bd-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="585bd-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="585bd-109">Scope</span></span>   |<span data-ttu-id="585bd-110">エッジ</span><span class="sxs-lookup"><span data-stu-id="585bd-110">Edge</span></span>|
|<span data-ttu-id="585bd-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="585bd-111">Version</span></span>|<span data-ttu-id="585bd-112">4.5</span><span class="sxs-lookup"><span data-stu-id="585bd-112">4.5</span></span>|
|<span data-ttu-id="585bd-113">種類</span><span class="sxs-lookup"><span data-stu-id="585bd-113">Type</span></span>|<span data-ttu-id="585bd-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="585bd-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="585bd-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="585bd-115">Affected APIs</span></span>

-<xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=nameWithType></li></ul>|
