---
title: IMetaDataEmit::SetParamProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParamProps
helpviewer_keywords:
- IMetaDataEmit::SetParamProps method [.NET Framework metadata]
- SetParamProps method [.NET Framework metadata]
ms.assetid: a95a3908-9f87-4084-937e-8e01ef03ad63
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6b7cfba90edab44a0053fdfc759417ee7f074401
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59132035"
---
# <a name="imetadataemitsetparamprops-method"></a><span data-ttu-id="3ee17-102">IMetaDataEmit::SetParamProps メソッド</span><span class="sxs-lookup"><span data-stu-id="3ee17-102">IMetaDataEmit::SetParamProps Method</span></span>
<span data-ttu-id="3ee17-103">前回の呼び出しで定義されているメソッドのパラメーターの機能の変更を設定または[imetadataemit::defineparam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="3ee17-103">Sets or changes features of a method parameter that was defined by a prior call to [IMetaDataEmit::DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ee17-104">構文</span><span class="sxs-lookup"><span data-stu-id="3ee17-104">Syntax</span></span>  
  
```  
HRESULT SetParamProps (   
    [in]  mdParamDef  pd,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwParamFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ee17-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3ee17-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="3ee17-106">[in]ターゲットのパラメーターのトークンです。</span><span class="sxs-lookup"><span data-stu-id="3ee17-106">[in] The token for the target parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="3ee17-107">[in]Unicode でパラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="3ee17-107">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="3ee17-108">[in]パラメーターのフラグ。</span><span class="sxs-lookup"><span data-stu-id="3ee17-108">[in] The flags for the parameter.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="3ee17-109">[in]ELEMENT_TYPE_ \* 定数の値。</span><span class="sxs-lookup"><span data-stu-id="3ee17-109">[in] The ELEMENT_TYPE_\* for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="3ee17-110">[in]パラメーターの定数値。</span><span class="sxs-lookup"><span data-stu-id="3ee17-110">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="3ee17-111">[in] \(Unicode) 文字のサイズ`pValue`します。</span><span class="sxs-lookup"><span data-stu-id="3ee17-111">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ee17-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="3ee17-112">Requirements</span></span>  
 <span data-ttu-id="3ee17-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ee17-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ee17-114">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3ee17-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3ee17-115">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="3ee17-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="3ee17-116">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="3ee17-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3ee17-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ee17-117">See also</span></span>

- [<span data-ttu-id="3ee17-118">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3ee17-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="3ee17-119">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3ee17-119">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
