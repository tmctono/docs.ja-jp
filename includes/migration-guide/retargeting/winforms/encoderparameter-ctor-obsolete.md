---
ms.openlocfilehash: 4ad7c4c2781480c08ad4cf27e40de445b1c50671
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617244"
---
### <a name="encoderparameter-ctor-is-obsolete"></a><span data-ttu-id="de0f4-101">EncoderParameter ctor が廃止に</span><span class="sxs-lookup"><span data-stu-id="de0f4-101">EncoderParameter ctor is obsolete</span></span>

#### <a name="details"></a><span data-ttu-id="de0f4-102">説明</span><span class="sxs-lookup"><span data-stu-id="de0f4-102">Details</span></span>

<span data-ttu-id="de0f4-103"><xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)> コンストラクターは廃止され、使用された場合、ビルド警告が発生します。</span><span class="sxs-lookup"><span data-stu-id="de0f4-103">The <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)> constructor is obsolete now and will introduce build warnings if used.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="de0f4-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="de0f4-104">Suggestion</span></span>

<span data-ttu-id="de0f4-105">コンストラクター <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)> は引き続き動作しますが、.NET Framework 4.5 のツールでコードを再コンパイルするときに古いビルド警告を回避するには、コンストラクター <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Drawing.Imaging.EncoderParameterValueType,System.IntPtr)> を代わりに使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de0f4-105">Although the <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)>constructor will continue to work, the following constructor should be used instead to avoid the obsolete build warning when re-compiling code with .NET Framework  4.5 tools: <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Drawing.Imaging.EncoderParameterValueType,System.IntPtr)>.</span></span>

| <span data-ttu-id="de0f4-106">名前</span><span class="sxs-lookup"><span data-stu-id="de0f4-106">Name</span></span>    | <span data-ttu-id="de0f4-107">[値]</span><span class="sxs-lookup"><span data-stu-id="de0f4-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="de0f4-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="de0f4-108">Scope</span></span>   | <span data-ttu-id="de0f4-109">マイナー</span><span class="sxs-lookup"><span data-stu-id="de0f4-109">Minor</span></span>       |
| <span data-ttu-id="de0f4-110">バージョン</span><span class="sxs-lookup"><span data-stu-id="de0f4-110">Version</span></span> | <span data-ttu-id="de0f4-111">4.5</span><span class="sxs-lookup"><span data-stu-id="de0f4-111">4.5</span></span>         |
| <span data-ttu-id="de0f4-112">種類</span><span class="sxs-lookup"><span data-stu-id="de0f4-112">Type</span></span>    | <span data-ttu-id="de0f4-113">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="de0f4-113">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="de0f4-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="de0f4-114">Affected APIs</span></span>

- <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)>
