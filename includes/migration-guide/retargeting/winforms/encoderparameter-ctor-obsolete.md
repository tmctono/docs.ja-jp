---
ms.openlocfilehash: b4e062fe3a00b76da144e706841f87b2a95888e5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774326"
---
### <a name="encoderparameter-ctor-is-obsolete"></a><span data-ttu-id="02f73-101">EncoderParameter ctor が廃止に</span><span class="sxs-lookup"><span data-stu-id="02f73-101">EncoderParameter ctor is obsolete</span></span>

|   |   |
|---|---|
|<span data-ttu-id="02f73-102">説明</span><span class="sxs-lookup"><span data-stu-id="02f73-102">Details</span></span>|<span data-ttu-id="02f73-103"><xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)> コンストラクターは廃止され、使用された場合、ビルド警告が発生します。</span><span class="sxs-lookup"><span data-stu-id="02f73-103">The <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)> constructor is obsolete now and will introduce build warnings if used.</span></span>|
|<span data-ttu-id="02f73-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="02f73-104">Suggestion</span></span>|<span data-ttu-id="02f73-105">コンストラクター <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)> は引き続き動作しますが、.NET Framework 4.5 のツールでコードを再コンパイルするときに古いビルド警告を回避するには、コンストラクター <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Drawing.Imaging.EncoderParameterValueType,System.IntPtr)> を代わりに使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="02f73-105">Although the <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)>constructor will continue to work, the following constructor should be used instead to avoid the obsolete build warning when re-compiling code with .NET Framework  4.5 tools: <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Drawing.Imaging.EncoderParameterValueType,System.IntPtr)>.</span></span>|
|<span data-ttu-id="02f73-106">スコープ</span><span class="sxs-lookup"><span data-stu-id="02f73-106">Scope</span></span>|<span data-ttu-id="02f73-107">マイナー</span><span class="sxs-lookup"><span data-stu-id="02f73-107">Minor</span></span>|
|<span data-ttu-id="02f73-108">Version</span><span class="sxs-lookup"><span data-stu-id="02f73-108">Version</span></span>|<span data-ttu-id="02f73-109">4.5</span><span class="sxs-lookup"><span data-stu-id="02f73-109">4.5</span></span>|
|<span data-ttu-id="02f73-110">型</span><span class="sxs-lookup"><span data-stu-id="02f73-110">Type</span></span>|<span data-ttu-id="02f73-111">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="02f73-111">Retargeting</span></span>|
|<span data-ttu-id="02f73-112">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="02f73-112">Affected APIs</span></span>|<ul><li><xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)?displayProperty=nameWithType></li></ul>|
