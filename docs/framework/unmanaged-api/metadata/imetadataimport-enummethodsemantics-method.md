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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6021cd0126f4dd85b796a3110cd95a83c0f77ff4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466792"
---
# <a name="imetadataimportenummethodsemantics-method"></a><span data-ttu-id="d9a73-102">IMetaDataImport::EnumMethodSemantics メソッド</span><span class="sxs-lookup"><span data-stu-id="d9a73-102">IMetaDataImport::EnumMethodSemantics Method</span></span>
<span data-ttu-id="d9a73-103">指定したメソッドが関連付けられているプロパティおよびプロパティ変更イベントを列挙します。</span><span class="sxs-lookup"><span data-stu-id="d9a73-103">Enumerates the properties and the property-change events to which the specified method is related.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9a73-104">構文</span><span class="sxs-lookup"><span data-stu-id="d9a73-104">Syntax</span></span>  
  
```  
HRESULT EnumMethodSemantics (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,   
   [out] mdToken         rEventProp[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcEventProp  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9a73-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d9a73-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="d9a73-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="d9a73-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="d9a73-107">このメソッドの最初の呼び出しで NULL があります。</span><span class="sxs-lookup"><span data-stu-id="d9a73-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="d9a73-108">[in]列挙体のスコープを制限する MethodDef トークンです。</span><span class="sxs-lookup"><span data-stu-id="d9a73-108">[in] A MethodDef token that limits the scope of the enumeration.</span></span>  
  
 `rEventProp`  
 <span data-ttu-id="d9a73-109">[out]イベントまたはプロパティを格納する配列。</span><span class="sxs-lookup"><span data-stu-id="d9a73-109">[out] The array used to store the events or properties.</span></span>  
  
 `cMax`  
 <span data-ttu-id="d9a73-110">[in] `rEventProp` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="d9a73-110">[in] The maximum size of the `rEventProp` array.</span></span>  
  
 `pcEventProp`  
 <span data-ttu-id="d9a73-111">[out]イベントまたはプロパティで返される数`rEventProp`します。</span><span class="sxs-lookup"><span data-stu-id="d9a73-111">[out] The number of events or properties returned in `rEventProp`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d9a73-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="d9a73-112">Return Value</span></span>  
  
|<span data-ttu-id="d9a73-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d9a73-113">HRESULT</span></span>|<span data-ttu-id="d9a73-114">説明</span><span class="sxs-lookup"><span data-stu-id="d9a73-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="d9a73-115">`EnumMethodSemantics` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="d9a73-115">`EnumMethodSemantics` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="d9a73-116">イベントまたはプロパティを列挙するためにはありません。</span><span class="sxs-lookup"><span data-stu-id="d9a73-116">There are no events or properties to enumerate.</span></span> <span data-ttu-id="d9a73-117">その場合は、`pcEventProp`は 0 です。</span><span class="sxs-lookup"><span data-stu-id="d9a73-117">In that case, `pcEventProp` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9a73-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="d9a73-118">Remarks</span></span>  
 <span data-ttu-id="d9a73-119">多くの共通言語ランタイム型を定義*プロパティ*`Changed`イベントと`On`*プロパティ*`Changed`それらのプロパティに関連するメソッド。</span><span class="sxs-lookup"><span data-stu-id="d9a73-119">Many common language runtime types define *Property*`Changed` events and `On`*Property*`Changed` methods related to their properties.</span></span> <span data-ttu-id="d9a73-120">たとえば、<xref:System.Windows.Forms.Control?displayProperty=nameWithType>型を定義しますを<xref:System.Windows.Forms.Control.Font%2A>プロパティ、<xref:System.Windows.Forms.Control.FontChanged>イベント、および<xref:System.Windows.Forms.Control.OnFontChanged%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="d9a73-120">For example, the <xref:System.Windows.Forms.Control?displayProperty=nameWithType> type defines a <xref:System.Windows.Forms.Control.Font%2A> property, a <xref:System.Windows.Forms.Control.FontChanged> event, and an <xref:System.Windows.Forms.Control.OnFontChanged%2A> method.</span></span> <span data-ttu-id="d9a73-121">Set アクセサー メソッド、<xref:System.Windows.Forms.Control.Font%2A>プロパティ呼び出し<xref:System.Windows.Forms.Control.OnFontChanged%2A>メソッドを生成させる、<xref:System.Windows.Forms.Control.FontChanged>イベント。</span><span class="sxs-lookup"><span data-stu-id="d9a73-121">The set accessor method of the <xref:System.Windows.Forms.Control.Font%2A> property calls <xref:System.Windows.Forms.Control.OnFontChanged%2A> method, which in turn raises the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span> <span data-ttu-id="d9a73-122">呼び出しは`EnumMethodSemantics`の MethodDef を使用して<xref:System.Windows.Forms.Control.OnFontChanged%2A>への参照を取得する、<xref:System.Windows.Forms.Control.Font%2A>プロパティおよび<xref:System.Windows.Forms.Control.FontChanged>イベント。</span><span class="sxs-lookup"><span data-stu-id="d9a73-122">You would call `EnumMethodSemantics` using the MethodDef for <xref:System.Windows.Forms.Control.OnFontChanged%2A> to get references to the <xref:System.Windows.Forms.Control.Font%2A> property and the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9a73-123">必要条件</span><span class="sxs-lookup"><span data-stu-id="d9a73-123">Requirements</span></span>  
 <span data-ttu-id="d9a73-124">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9a73-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9a73-125">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d9a73-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d9a73-126">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="d9a73-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d9a73-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9a73-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9a73-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9a73-128">See also</span></span>
- [<span data-ttu-id="d9a73-129">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d9a73-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="d9a73-130">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d9a73-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
