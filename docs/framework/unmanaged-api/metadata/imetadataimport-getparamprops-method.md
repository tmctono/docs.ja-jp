---
title: IMetaDataImport::GetParamProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetParamProps
helpviewer_keywords:
- IMetaDataImport::GetParamProps method [.NET Framework metadata]
- GetParamProps method [.NET Framework metadata]
ms.assetid: 4d5e5f00-bcab-4f41-b191-176511a186a7
topic_type:
- apiref
ms.openlocfilehash: bb73ccdd9eee4b5a655a56b5d6757e0c6003fbc9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437125"
---
# <a name="imetadataimportgetparamprops-method"></a><span data-ttu-id="e5abd-102">IMetaDataImport::GetParamProps メソッド</span><span class="sxs-lookup"><span data-stu-id="e5abd-102">IMetaDataImport::GetParamProps Method</span></span>
<span data-ttu-id="e5abd-103">指定した ParamDef トークンによって参照されるパラメーターのメタデータ値を取得します。</span><span class="sxs-lookup"><span data-stu-id="e5abd-103">Gets metadata values for the parameter referenced by the specified ParamDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5abd-104">構文</span><span class="sxs-lookup"><span data-stu-id="e5abd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetParamProps (  
   [in]  mdParamDef      tk,  
   [out] mdMethodDef     *pmd,  
   [out] ULONG           *pulSequence,  
   [out] LPWSTR          szName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName,  
   [out] DWORD           *pdwAttr,  
   [out] DWORD           *pdwCPlusTypeFlag,  
   [out] UVCP_CONSTANT   *ppValue,  
   [out] ULONG           *pcchValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5abd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e5abd-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="e5abd-106">からメタデータを返すパラメーターを表す ParamDef トークン。</span><span class="sxs-lookup"><span data-stu-id="e5abd-106">[in] A ParamDef token that represents the parameter to return metadata for.</span></span>  
  
 `pmd`  
 <span data-ttu-id="e5abd-107">入出力パラメーターを受け取るメソッドを表す MethodDef トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e5abd-107">[out] A pointer to a MethodDef token representing the method that takes the parameter.</span></span>  
  
 `pulSequence`  
 <span data-ttu-id="e5abd-108">入出力メソッド引数リスト内のパラメーターの序数位置。</span><span class="sxs-lookup"><span data-stu-id="e5abd-108">[out] The ordinal position of the parameter in the method argument list.</span></span>  
  
 `szName`  
 <span data-ttu-id="e5abd-109">入出力パラメーターの名前を保持するバッファー。</span><span class="sxs-lookup"><span data-stu-id="e5abd-109">[out] A buffer to hold the name of the parameter.</span></span>  
  
 `cchName`  
 <span data-ttu-id="e5abd-110">から`szName`のワイド文字で要求されたサイズ。</span><span class="sxs-lookup"><span data-stu-id="e5abd-110">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="e5abd-111">入出力`szName`のワイド文字で返されたサイズ。</span><span class="sxs-lookup"><span data-stu-id="e5abd-111">[out] The returned size in wide characters of `szName`.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="e5abd-112">入出力パラメーターに関連付けられているすべての属性フラグへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e5abd-112">[out] A pointer to any attribute flags associated with the parameter.</span></span> <span data-ttu-id="e5abd-113">これは `CorParamAttr` 値のビットマスクです。</span><span class="sxs-lookup"><span data-stu-id="e5abd-113">This is a bitmask of `CorParamAttr` values.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="e5abd-114">入出力パラメーターが <xref:System.ValueType>であることを示すフラグへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e5abd-114">[out] A pointer to a flag specifying that the parameter is a <xref:System.ValueType>.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="e5abd-115">入出力パラメーターによって返される定数文字列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="e5abd-115">[out] A pointer to a constant string returned by the parameter.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="e5abd-116">入出力ワイド文字の `ppValue` のサイズ。 `ppValue` が文字列を保持していない場合は0。</span><span class="sxs-lookup"><span data-stu-id="e5abd-116">[out] The size of `ppValue` in wide characters, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5abd-117">コメント</span><span class="sxs-lookup"><span data-stu-id="e5abd-117">Remarks</span></span>

<span data-ttu-id="e5abd-118">`pulSequence` のシーケンス値は、パラメーターに対して1から始まります。</span><span class="sxs-lookup"><span data-stu-id="e5abd-118">The sequence values in `pulSequence` begin with 1 for parameters.</span></span> <span data-ttu-id="e5abd-119">戻り値のシーケンス番号は0です。</span><span class="sxs-lookup"><span data-stu-id="e5abd-119">A return value has a sequence number of 0.</span></span>

## <a name="requirements"></a><span data-ttu-id="e5abd-120">要件</span><span class="sxs-lookup"><span data-stu-id="e5abd-120">Requirements</span></span>  
 <span data-ttu-id="e5abd-121">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5abd-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5abd-122">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="e5abd-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e5abd-123">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="e5abd-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e5abd-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5abd-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5abd-125">参照</span><span class="sxs-lookup"><span data-stu-id="e5abd-125">See also</span></span>

- [<span data-ttu-id="e5abd-126">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5abd-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="e5abd-127">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5abd-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
