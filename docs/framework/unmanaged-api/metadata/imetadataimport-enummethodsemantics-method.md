---
title: IMetaDataImport::EnumMethodSemantics メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodSemantics
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodSemantics
helpviewer_keywords:
- EnumMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::EnumMethodSemantics method [.NET Framework metadata]
ms.assetid: e7e3c630-9691-46d6-94df-b5593a7bb08a
topic_type:
- apiref
ms.openlocfilehash: 213cbd955e3d47a49abde579a54af48641e225ec
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491928"
---
# <a name="imetadataimportenummethodsemantics-method"></a><span data-ttu-id="e7d2e-102">IMetaDataImport::EnumMethodSemantics メソッド</span><span class="sxs-lookup"><span data-stu-id="e7d2e-102">IMetaDataImport::EnumMethodSemantics Method</span></span>
<span data-ttu-id="e7d2e-103">指定したメソッドが関連付けられているプロパティおよびプロパティ変更イベントを列挙します。</span><span class="sxs-lookup"><span data-stu-id="e7d2e-103">Enumerates the properties and the property-change events to which the specified method is related.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7d2e-104">構文</span><span class="sxs-lookup"><span data-stu-id="e7d2e-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodSemantics (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,
   [out] mdToken         rEventProp[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcEventProp  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7d2e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e7d2e-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="e7d2e-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="e7d2e-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="e7d2e-107">このメソッドの最初の呼び出しでは、この値は NULL である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7d2e-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="e7d2e-108">から列挙型のスコープを制限する MethodDef トークン。</span><span class="sxs-lookup"><span data-stu-id="e7d2e-108">[in] A MethodDef token that limits the scope of the enumeration.</span></span>  
  
 `rEventProp`  
 <span data-ttu-id="e7d2e-109">入出力イベントまたはプロパティを格納するために使用される配列。</span><span class="sxs-lookup"><span data-stu-id="e7d2e-109">[out] The array used to store the events or properties.</span></span>  
  
 `cMax`  
 <span data-ttu-id="e7d2e-110">[in] `rEventProp` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="e7d2e-110">[in] The maximum size of the `rEventProp` array.</span></span>  
  
 `pcEventProp`  
 <span data-ttu-id="e7d2e-111">入出力で返されたイベントまたはプロパティの数 `rEventProp` 。</span><span class="sxs-lookup"><span data-stu-id="e7d2e-111">[out] The number of events or properties returned in `rEventProp`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e7d2e-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="e7d2e-112">Return Value</span></span>  
  
|<span data-ttu-id="e7d2e-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e7d2e-113">HRESULT</span></span>|<span data-ttu-id="e7d2e-114">説明</span><span class="sxs-lookup"><span data-stu-id="e7d2e-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="e7d2e-115">`EnumMethodSemantics`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="e7d2e-115">`EnumMethodSemantics` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="e7d2e-116">列挙するイベントやプロパティはありません。</span><span class="sxs-lookup"><span data-stu-id="e7d2e-116">There are no events or properties to enumerate.</span></span> <span data-ttu-id="e7d2e-117">この場合、 `pcEventProp` は0になります。</span><span class="sxs-lookup"><span data-stu-id="e7d2e-117">In that case, `pcEventProp` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7d2e-118">解説</span><span class="sxs-lookup"><span data-stu-id="e7d2e-118">Remarks</span></span>  
 <span data-ttu-id="e7d2e-119">多くの共通言語ランタイム型*Property* `Changed` では、プロパティイベントとプロパティ `On` *Property* `Changed` に関連するプロパティメソッドが定義されています。</span><span class="sxs-lookup"><span data-stu-id="e7d2e-119">Many common language runtime types define *Property*`Changed` events and `On`*Property*`Changed` methods related to their properties.</span></span> <span data-ttu-id="e7d2e-120">たとえば、型は、 <xref:System.Windows.Forms.Control?displayProperty=nameWithType> <xref:System.Windows.Forms.Control.Font%2A> プロパティ、 <xref:System.Windows.Forms.Control.FontChanged> イベント、およびメソッドを定義し <xref:System.Windows.Forms.Control.OnFontChanged%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="e7d2e-120">For example, the <xref:System.Windows.Forms.Control?displayProperty=nameWithType> type defines a <xref:System.Windows.Forms.Control.Font%2A> property, a <xref:System.Windows.Forms.Control.FontChanged> event, and an <xref:System.Windows.Forms.Control.OnFontChanged%2A> method.</span></span> <span data-ttu-id="e7d2e-121">プロパティの set アクセサーメソッドは、メソッドを呼び出します。このメソッドは、 <xref:System.Windows.Forms.Control.Font%2A> イベントを発生さ <xref:System.Windows.Forms.Control.OnFontChanged%2A> せ <xref:System.Windows.Forms.Control.FontChanged> ます。</span><span class="sxs-lookup"><span data-stu-id="e7d2e-121">The set accessor method of the <xref:System.Windows.Forms.Control.Font%2A> property calls <xref:System.Windows.Forms.Control.OnFontChanged%2A> method, which in turn raises the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span> <span data-ttu-id="e7d2e-122">`EnumMethodSemantics` <xref:System.Windows.Forms.Control.OnFontChanged%2A> プロパティとイベントへの参照を取得するには、の MethodDef を使用してを呼び出し <xref:System.Windows.Forms.Control.Font%2A> <xref:System.Windows.Forms.Control.FontChanged> ます。</span><span class="sxs-lookup"><span data-stu-id="e7d2e-122">You would call `EnumMethodSemantics` using the MethodDef for <xref:System.Windows.Forms.Control.OnFontChanged%2A> to get references to the <xref:System.Windows.Forms.Control.Font%2A> property and the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7d2e-123">要件</span><span class="sxs-lookup"><span data-stu-id="e7d2e-123">Requirements</span></span>  
 <span data-ttu-id="e7d2e-124">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7d2e-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7d2e-125">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="e7d2e-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e7d2e-126">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="e7d2e-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e7d2e-127">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7d2e-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7d2e-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="e7d2e-128">See also</span></span>

- [<span data-ttu-id="e7d2e-129">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e7d2e-129">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="e7d2e-130">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e7d2e-130">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
