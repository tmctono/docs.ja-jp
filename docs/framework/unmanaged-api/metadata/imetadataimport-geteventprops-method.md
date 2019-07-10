---
title: IMetaDataImport::GetEventProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetEventProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetEventProps
helpviewer_keywords:
- IMetaDataImport::GetEventProps method [.NET Framework metadata]
- GetEventProps method [.NET Framework metadata]
ms.assetid: 5eaf3b4a-92b7-4d5b-97e0-1e83721e0052
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c87f2212c761dc31a75addabca6970c5497aa2a0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782427"
---
# <a name="imetadataimportgeteventprops-method"></a><span data-ttu-id="45abf-102">IMetaDataImport::GetEventProps メソッド</span><span class="sxs-lookup"><span data-stu-id="45abf-102">IMetaDataImport::GetEventProps Method</span></span>
<span data-ttu-id="45abf-103">宣言する型の追加と削除メソッドのデリゲート、任意のフラグと関連付けられているその他のデータを含め、指定したイベント トークンによって表されるイベントのメタデータ情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="45abf-103">Gets metadata information for the event represented by the specified event token, including the declaring type, the add and remove methods for delegates, and any flags and other associated data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45abf-104">構文</span><span class="sxs-lookup"><span data-stu-id="45abf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetEventProps (  
   [in]  mdEvent       ev,  
   [out] mdTypeDef     *pClass,   
   [out] LPCWSTR       szEvent,   
   [in]  ULONG         cchEvent,   
   [out] ULONG         *pchEvent,   
   [out] DWORD         *pdwEventFlags,  
   [out] mdToken       *ptkEventType,  
   [out] mdMethodDef   *pmdAddOn,   
   [out] mdMethodDef   *pmdRemoveOn,   
   [out] mdMethodDef   *pmdFire,   
   [out] mdMethodDef   rmdOtherMethod[],   
   [in]  ULONG         cMax,  
   [out] ULONG         *pcOtherMethod  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45abf-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="45abf-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="45abf-106">[in]メタデータを取得するイベントを表すイベントのメタデータ トークンです。</span><span class="sxs-lookup"><span data-stu-id="45abf-106">[in] The event metadata token representing the event to get metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="45abf-107">[out]イベントを宣言するクラスを表す TypeDef トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="45abf-107">[out] A pointer to the TypeDef token representing the class that declares the event.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="45abf-108">[out]によって参照されるイベントの名前`ev`します。</span><span class="sxs-lookup"><span data-stu-id="45abf-108">[out] The name of the event referenced by `ev`.</span></span>  
  
 `pchEvent`  
 <span data-ttu-id="45abf-109">[in]要求された長さのワイド文字で`szEvent`します。</span><span class="sxs-lookup"><span data-stu-id="45abf-109">[in] The requested length in wide characters of `szEvent`.</span></span>  
  
 `pdwEventFlags`  
 <span data-ttu-id="45abf-110">[out]ワイド文字で返される長さ`szEvent`します。</span><span class="sxs-lookup"><span data-stu-id="45abf-110">[out] The returned length in wide characters of `szEvent`.</span></span>  
  
 `ptkEventType`  
 <span data-ttu-id="45abf-111">[out]TypeRef または TypeDef メタデータ トークンを表すへのポインター、<xref:System.Delegate>イベントの種類。</span><span class="sxs-lookup"><span data-stu-id="45abf-111">[out] A pointer to a TypeRef or TypeDef metadata token representing the <xref:System.Delegate> type of the event.</span></span>  
  
 `pmdAddOn`  
 <span data-ttu-id="45abf-112">[out]イベントのハンドラーを追加するメソッドを表すメタデータ トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="45abf-112">[out] A pointer to the metadata token representing the method that adds handlers for the event.</span></span>  
  
 `pmdRemoveOn`  
 <span data-ttu-id="45abf-113">[out]イベントのハンドラーを削除するメソッドを表すメタデータ トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="45abf-113">[out] A pointer to the metadata token representing the method that removes handlers for the event.</span></span>  
  
 `pmdFire`  
 <span data-ttu-id="45abf-114">[out]イベントを発生させるメソッドを表すメタデータ トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="45abf-114">[out] A pointer to the metadata token representing the method that raises the event.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="45abf-115">[out]イベントに関連付けられているその他のメソッドへのトークンのポインターの配列。</span><span class="sxs-lookup"><span data-stu-id="45abf-115">[out] An array of token pointers to other methods associated with the event.</span></span>  
  
 `cMax`  
 <span data-ttu-id="45abf-116">[in] `rmdOtherMethod` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="45abf-116">[in] The maximum size of the `rmdOtherMethod` array.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="45abf-117">[out]トークンで返される数`rmdOtherMethod`します。</span><span class="sxs-lookup"><span data-stu-id="45abf-117">[out] The number of tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45abf-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="45abf-118">Requirements</span></span>  
 <span data-ttu-id="45abf-119">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="45abf-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45abf-120">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="45abf-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="45abf-121">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="45abf-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="45abf-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45abf-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45abf-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="45abf-123">See also</span></span>

- [<span data-ttu-id="45abf-124">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="45abf-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="45abf-125">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="45abf-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
