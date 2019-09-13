---
title: GUID_ManagedName 属性
ms.date: 03/30/2017
api_name:
- GUID_ManagedName
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GUID_ManagedName
helpviewer_keywords:
- GUID_ManagedName attribute
ms.assetid: 11e18095-e444-47bc-aff6-b887ac5dc01e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f14d00f17a61576a50e26d3cbcf734a10ed3c03a
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/11/2019
ms.locfileid: "70895020"
---
# <a name="guid_managedname-attribute"></a><span data-ttu-id="0f2fd-102">GUID_ManagedName 属性</span><span class="sxs-lookup"><span data-stu-id="0f2fd-102">GUID_ManagedName Attribute</span></span>
<span data-ttu-id="0f2fd-103">コンポーネントオブジェクトモデル (COM) ライブラリのマネージ名前空間名を指定するカスタムインターフェイス属性を定義します。</span><span class="sxs-lookup"><span data-stu-id="0f2fd-103">Defines a custom interface attribute that specifies the managed namespace name for a component object model (COM) library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f2fd-104">構文</span><span class="sxs-lookup"><span data-stu-id="0f2fd-104">Syntax</span></span>  
  
```idl
[  
   custom(GUID_ManagedName, value)  
]  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f2fd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0f2fd-105">Parameters</span></span>  
 `value`  
 <span data-ttu-id="0f2fd-106">ライブラリのマネージ名前空間の名前。</span><span class="sxs-lookup"><span data-stu-id="0f2fd-106">The managed namespace name for the library.</span></span>  
  
## <a name="definition"></a><span data-ttu-id="0f2fd-107">定義</span><span class="sxs-lookup"><span data-stu-id="0f2fd-107">Definition</span></span>  
 <span data-ttu-id="0f2fd-108">`GUID_ManagedName`は、Cor で次のように定義されています。</span><span class="sxs-lookup"><span data-stu-id="0f2fd-108">`GUID_ManagedName` is defined in Cor.h as follows:</span></span>  
  
```cpp
// {0F21F359-AB84-41e8-9A78-36D110E6D2F9}  
EXTERN_GUID(GUID_ManagedName, 0xf21f359, 0xab84, 0x41e8, 0x9a, 0x78, 0x36, 0xd1, 0x10, 0xe6, 0xd2, 0xf9);  
```  
  
## <a name="remarks"></a><span data-ttu-id="0f2fd-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="0f2fd-109">Remarks</span></span>  
 <span data-ttu-id="0f2fd-110">カスタムインターフェイス属性は、タイプライブラリ内のオブジェクトのメタデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="0f2fd-110">A custom interface attribute defines metadata for an object in the type library.</span></span>  
  
 <span data-ttu-id="0f2fd-111">属性<xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType>から<xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType>マネージ名を取得するには、またはを使用します。</span><span class="sxs-lookup"><span data-stu-id="0f2fd-111">Use <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType> or <xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType> to retrieve the managed name from the attribute.</span></span>  
  
 <span data-ttu-id="0f2fd-112">詳細については、ビジュアルC++リファレンスドキュメントの「[インターフェイス属性](/cpp/windows/attributes/interface-attributes)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f2fd-112">For more information, see [Interface Attributes](/cpp/windows/attributes/interface-attributes) in the Visual C++ reference documentation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f2fd-113">例</span><span class="sxs-lookup"><span data-stu-id="0f2fd-113">Example</span></span>  
 <span data-ttu-id="0f2fd-114">次の例は、 `GUID_ManagedName`属性を使用したライブラリ定義を示しています。</span><span class="sxs-lookup"><span data-stu-id="0f2fd-114">The following example shows a library definition using the `GUID_ManagedName` attribute.</span></span>  
  
```idl
[  
   ...  
   custom(GUID_ManagedName, Microsoft.VisualStudio.CommandBars.dll")  
]  
library Microsoft_VisualStudio_CommandBars  
{  
   ...  
}  
```  
  
## <a name="requirements"></a><span data-ttu-id="0f2fd-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="0f2fd-115">Requirements</span></span>  
 <span data-ttu-id="0f2fd-116">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="0f2fd-116">**Header:** Cor.h</span></span>
