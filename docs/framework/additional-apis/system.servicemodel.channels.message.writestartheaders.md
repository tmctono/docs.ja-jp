---
title: WriteStartHeaders メソッド (System.servicemodel. Channels)
ms.date: 11/01/2019
topic_type:
- apiref
api_name:
- System.ServiceModel.Channels.Message.WriteStartHeaders
api_location:
- system.servicemodel.dll
api_type:
- Assembly
ms.openlocfilehash: c826e6a3b976e5705e9815586441e8a25b64f76e
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214865"
---
# <a name="messagewritestartheaders-method"></a><span data-ttu-id="30cf8-102">WriteStartHeaders メソッド</span><span class="sxs-lookup"><span data-stu-id="30cf8-102">Message.WriteStartHeaders Method</span></span>

<span data-ttu-id="30cf8-103"><xref:System.ServiceModel.Channels.Message.OnWriteStartHeaders%2A?displayProperty=nameWithType> メソッドを呼び出すことによって、開始ヘッダーを XML ファイルに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="30cf8-103">Writes the start header into an XML file by calling the <xref:System.ServiceModel.Channels.Message.OnWriteStartHeaders%2A?displayProperty=nameWithType> method.</span></span>

```csharp
internal void WriteStartHeaders(XmlDictionaryWriter writer)
```

## <a name="parameters"></a><span data-ttu-id="30cf8-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="30cf8-104">Parameters</span></span>

- <span data-ttu-id="30cf8-105">`writer` <xref:System.Xml.XmlDictionaryWriter></span><span class="sxs-lookup"><span data-stu-id="30cf8-105">`writer` <xref:System.Xml.XmlDictionaryWriter></span></span>\
  <span data-ttu-id="30cf8-106">開始ヘッダーを XML ファイルに書き込むために使用するライター。</span><span class="sxs-lookup"><span data-stu-id="30cf8-106">The writer that is used to write the start header into an XML file.</span></span>

## <a name="remarks"></a><span data-ttu-id="30cf8-107">コメント</span><span class="sxs-lookup"><span data-stu-id="30cf8-107">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="30cf8-108">`Message.WriteStartHeaders` メソッドは内部であり、コードで直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="30cf8-108">The `Message.WriteStartHeaders` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="30cf8-109">Microsoft では、どのような状況でも、実稼働アプリケーションでこの方法を使用することはサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="30cf8-109">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="30cf8-110">要件</span><span class="sxs-lookup"><span data-stu-id="30cf8-110">Requirements</span></span>

<span data-ttu-id="30cf8-111">**名前空間:** <xref:System.ServiceModel.Channels></span><span class="sxs-lookup"><span data-stu-id="30cf8-111">**Namespace:** <xref:System.ServiceModel.Channels></span></span>

<span data-ttu-id="30cf8-112">**アセンブリ:** System.servicemodel</span><span class="sxs-lookup"><span data-stu-id="30cf8-112">**Assembly:** System.ServiceModel.dll</span></span>

<span data-ttu-id="30cf8-113">**.NET Framework のバージョン:** 3.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="30cf8-113">**.NET Framework versions:** Available since 3.0.</span></span>
