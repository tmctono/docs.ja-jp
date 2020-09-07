---
ms.openlocfilehash: 58dbb54d42d89b450134758072e3133ae4e6b13d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497585"
---
### <a name="systemthreadingtaskstask-no-longer-throw-objectdisposedexception-after-object-is-disposed"></a>System.Threading.Tasks.Task は、オブジェクトが破棄された後、ObjectDisposedException をスローしなくなりました

#### <a name="details"></a>説明

<xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle>を除き、<xref:System.Threading.Tasks.Task?displayProperty=fullName> メソッドでオブジェクトが破棄された後も <xref:System.ObjectDisposedException?displayProperty=fullName> の例外がスローされることがなくなりました。この変更により、キャッシュされたタスクを使用できるようになりました。 たとえば、メソッドで新しいタスクを割り当てる代わりに、既に完了した操作を表す、キャッシュされたタスクを返すことができます。 これは、タスクの任意のコンシューマーによって破棄されてしまうと、使用不可能になってしまう以前の .NET Framework のバージョンでは不可能でした。

#### <a name="suggestion"></a>提案される解決策

オブジェクトが破棄されたとき、Task メソッドが <xref:System.ObjectDisposedException?displayProperty=fullName> をスローしなくなったことに注意してください。 アプリが、タスクが破棄されたことを確認するために、この例外に依存していた場合は、<xref:System.Threading.Tasks.Task.Status> を使用してタスクのステータスを明示的に確認するように、アプリを更新する必要があります。

| 名前    | [値]       |
|:--------|:------------|
| スコープ   |マイナー|
|バージョン|4.5|
|種類|ランタイム|

#### <a name="affected-apis"></a>影響を受ける API

API 分析では検出できません。

<!--

#### Affected APIs

Not detectable via API analysis.

-->
