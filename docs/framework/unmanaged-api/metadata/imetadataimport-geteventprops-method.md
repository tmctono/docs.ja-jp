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
ms.openlocfilehash: 306c1748b4997309ee15fb7751bc818b0287aaf0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177266"
---
# <a name="imetadataimportgeteventprops-method"></a><span data-ttu-id="a8b6c-102">IMetaDataImport::GetEventProps メソッド</span><span class="sxs-lookup"><span data-stu-id="a8b6c-102">IMetaDataImport::GetEventProps Method</span></span>
<span data-ttu-id="a8b6c-103">宣言型、デリゲートの add メソッドと remove メソッド、フラグおよびその他の関連付けられたデータなど、指定したイベント トークンによって表されるイベントのメタデータ情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="a8b6c-103">Gets metadata information for the event represented by the specified event token, including the declaring type, the add and remove methods for delegates, and any flags and other associated data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8b6c-104">構文</span><span class="sxs-lookup"><span data-stu-id="a8b6c-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="a8b6c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a8b6c-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="a8b6c-106">[in]メタデータを取得するイベントを表すイベント メタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="a8b6c-106">[in] The event metadata token representing the event to get metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="a8b6c-107">[アウト]イベントを宣言するクラスを表す TypeDef トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a8b6c-107">[out] A pointer to the TypeDef token representing the class that declares the event.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="a8b6c-108">[アウト]によって`ev`参照されるイベントの名前。</span><span class="sxs-lookup"><span data-stu-id="a8b6c-108">[out] The name of the event referenced by `ev`.</span></span>  
  
 `pchEvent`  
 <span data-ttu-id="a8b6c-109">[in]要求された長さは、 の`szEvent`ワイド文字で表示されます。</span><span class="sxs-lookup"><span data-stu-id="a8b6c-109">[in] The requested length in wide characters of `szEvent`.</span></span>  
  
 `pdwEventFlags`  
 <span data-ttu-id="a8b6c-110">[アウト]返される長さは、 の`szEvent`ワイド文字で返されます。</span><span class="sxs-lookup"><span data-stu-id="a8b6c-110">[out] The returned length in wide characters of `szEvent`.</span></span>  
  
 `ptkEventType`  
 <span data-ttu-id="a8b6c-111">[アウト]イベントの型を表す<xref:System.Delegate>TypeRef または TypeDef メタデータ トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a8b6c-111">[out] A pointer to a TypeRef or TypeDef metadata token representing the <xref:System.Delegate> type of the event.</span></span>  
  
 `pmdAddOn`  
 <span data-ttu-id="a8b6c-112">[アウト]イベントのハンドラーを追加するメソッドを表すメタデータ トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a8b6c-112">[out] A pointer to the metadata token representing the method that adds handlers for the event.</span></span>  
  
 `pmdRemoveOn`  
 <span data-ttu-id="a8b6c-113">[アウト]イベントのハンドラーを削除するメソッドを表すメタデータ トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a8b6c-113">[out] A pointer to the metadata token representing the method that removes handlers for the event.</span></span>  
  
 `pmdFire`  
 <span data-ttu-id="a8b6c-114">[アウト]イベントを発生させるメソッドを表すメタデータ トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a8b6c-114">[out] A pointer to the metadata token representing the method that raises the event.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="a8b6c-115">[アウト]イベントに関連付けられた他のメソッドへのトークン ポインターの配列。</span><span class="sxs-lookup"><span data-stu-id="a8b6c-115">[out] An array of token pointers to other methods associated with the event.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a8b6c-116">[in] `rmdOtherMethod` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="a8b6c-116">[in] The maximum size of the `rmdOtherMethod` array.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="a8b6c-117">[アウト]に返される`rmdOtherMethod`トークンの数。</span><span class="sxs-lookup"><span data-stu-id="a8b6c-117">[out] The number of tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8b6c-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="a8b6c-118">Requirements</span></span>  
 <span data-ttu-id="a8b6c-119">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8b6c-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8b6c-120">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="a8b6c-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a8b6c-121">**ライブラリ:** MsCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="a8b6c-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a8b6c-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8b6c-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8b6c-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="a8b6c-123">See also</span></span>

- [<span data-ttu-id="a8b6c-124">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a8b6c-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="a8b6c-125">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a8b6c-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
