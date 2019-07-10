---
title: IMetaDataImport::GetNameFromToken メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNameFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNameFromToken
helpviewer_keywords:
- GetNameFromToken method [.NET Framework metadata]
- IMetaDataImport::GetNameFromToken method [.NET Framework metadata]
ms.assetid: 32114ecf-8916-4ab2-a201-179c017344f1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fa6e8665e5e2194eb4a3dffad8e97a69deb202d0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778979"
---
# <a name="imetadataimportgetnamefromtoken-method"></a><span data-ttu-id="d7f39-102">IMetaDataImport::GetNameFromToken メソッド</span><span class="sxs-lookup"><span data-stu-id="d7f39-102">IMetaDataImport::GetNameFromToken Method</span></span>
<span data-ttu-id="d7f39-103">指定したメタデータ トークンによって参照されるオブジェクトの UTF-8 名を取得します。</span><span class="sxs-lookup"><span data-stu-id="d7f39-103">Gets the UTF-8 name of the object referenced by the specified metadata token.</span></span> <span data-ttu-id="d7f39-104">このメソッドは、互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="d7f39-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7f39-105">構文</span><span class="sxs-lookup"><span data-stu-id="d7f39-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNameFromToken (  
   [in] mdToken      tk,  
   [out] MDUTF8CSTR  *pszUtf8NamePtr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7f39-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d7f39-106">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="d7f39-107">[in]名前を取得するオブジェクトを表すトークンです。</span><span class="sxs-lookup"><span data-stu-id="d7f39-107">[in] The token representing the object to return the name for.</span></span>  
  
 `pszUtf8NamePtr`  
 <span data-ttu-id="d7f39-108">[out]ヒープで utf-8 オブジェクト名へのポインター。</span><span class="sxs-lookup"><span data-stu-id="d7f39-108">[out] A pointer to the UTF-8 object name in the heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7f39-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="d7f39-109">Remarks</span></span>  
 <span data-ttu-id="d7f39-110">`GetNameFromToken` は互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="d7f39-110">`GetNameFromToken` is obsolete.</span></span> <span data-ttu-id="d7f39-111">代わりに、トークンを必要に応じてなどの特定の型のプロパティを取得するメソッドを呼び出す`GetFieldProps`フィールドまたは`GetMethodProps`メソッド。</span><span class="sxs-lookup"><span data-stu-id="d7f39-111">As an alternative, call a method to get the properties of the particular type of token required, such as `GetFieldProps` for a field or `GetMethodProps` for a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7f39-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="d7f39-112">Requirements</span></span>  
 <span data-ttu-id="d7f39-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7f39-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7f39-114">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d7f39-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d7f39-115">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="d7f39-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d7f39-116">**.NET framework のバージョン:** 1</span><span class="sxs-lookup"><span data-stu-id="d7f39-116">**.NET Framework Versions:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7f39-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="d7f39-117">See also</span></span>

- [<span data-ttu-id="d7f39-118">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d7f39-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="d7f39-119">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d7f39-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
