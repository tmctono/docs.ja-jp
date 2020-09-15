---
ms.openlocfilehash: 6bb3b11ef4e4cb6f6a039c97911b0acca862fe6f
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065192"
---
### <a name="ca2247-argument-to-taskcompletionsource-constructor-should-be-taskcreationoptions-value"></a>CA2247:TaskCompletionSource コンストラクターの引数は、TaskCreationOptions 値にする必要があります

.NET コード アナライザー ルール [CA2247](/visualstudio/code-quality/ca2247) は、.NET 5.0 以降では既定で有効になっています。 <xref:System.Threading.Tasks.TaskContinuationOptions> 型の引数を渡す <xref:System.Threading.Tasks.TaskCompletionSource%601> コンストラクターへの呼び出しに対して、ビルドの警告が生成されます。

#### <a name="change-description"></a>変更内容

.NET 5.0 以降、.NET SDK には [.NET ソース コード アナライザー](../../../../docs/fundamentals/productivity/code-analysis.md)が含まれています。 これらのルールのいくつかは、[CA2247](/visualstudio/code-quality/ca2247) を含め、既定で有効になっています。 このルールに違反し、警告をエラーとして扱うように構成されているコードがプロジェクトに含まれている場合、この変更によってビルドが破損する可能性があります。

ルール CA2247 によって、<xref:System.Threading.Tasks.TaskContinuationOptions> 型の引数を渡す <xref:System.Threading.Tasks.TaskCompletionSource%601> コンストラクターへの呼び出しが検索されます。 <xref:System.Threading.Tasks.TaskCompletionSource%601> 型には、<xref:System.Threading.Tasks.TaskCreationOptions> 値を受け入れるコンストラクターと、<xref:System.Object> を受け入れる別のコンストラクターがあります。 <xref:System.Threading.Tasks.TaskCreationOptions> 値ではなく <xref:System.Threading.Tasks.TaskContinuationOptions> 値を誤って渡した場合、<xref:System.Object> パラメーターを持つコンストラクターが実行時に呼び出されます。 コードは、コンパイルされ、実行されますが、意図した動作を含みません。

#### <a name="version-introduced"></a>導入されたバージョン

5.0 Preview 8

#### <a name="recommended-action"></a>推奨アクション

- <xref:System.Threading.Tasks.TaskContinuationOptions> 引数を、対応する <xref:System.Threading.Tasks.TaskCreationOptions> 値に置き換えます。 ほぼ常にコード内のバグが強調表示されるため、この警告を表示しないでください。 詳細については、[CA2247](/visualstudio/code-quality/ca2247) に関する記事を参照してください。

- コード分析を完全に無効にするには、プロジェクト ファイルで `EnableNETAnalyzers` を `false` に設定します。 詳細については、「[EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers)」を参照してください。

#### <a name="category"></a>カテゴリ

コード分析

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.Threading.Tasks.TaskCompletionSource%601.%23ctor(System.Object)>

<!--

#### Affected APIs

- ``M:System.Threading.Tasks.TaskCompletionSource`1.#ctor(System.Object)``

-->
