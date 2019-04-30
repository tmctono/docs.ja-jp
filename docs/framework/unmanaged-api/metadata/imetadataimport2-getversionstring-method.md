---
title: IMetaDataImport2::GetVersionString メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetVersionString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetVersionString
helpviewer_keywords:
- GetVersionString method, IMetaDataImport2 interface [.NET Framework metadata]
- IMetaDataImport2::GetVersionString method [.NET Framework metadata]
ms.assetid: 308183ee-fd44-4432-9d86-ef00d181b49b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a01b4203145f6ffee4e3a11a3526f0b83e3dc741
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62042524"
---
# <a name="imetadataimport2getversionstring-method"></a><span data-ttu-id="c86a5-102">IMetaDataImport2::GetVersionString メソッド</span><span class="sxs-lookup"><span data-stu-id="c86a5-102">IMetaDataImport2::GetVersionString Method</span></span>
<span data-ttu-id="c86a5-103">アセンブリのビルドに使用されたランタイムのバージョン番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="c86a5-103">Gets the version number of the runtime that was used to build the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c86a5-104">構文</span><span class="sxs-lookup"><span data-stu-id="c86a5-104">Syntax</span></span>  
  
```  
HRESULT GetVersionString (  
   [out] LPWSTR      pwzBuf,  
   [in]  DWORD       ccBufSize,  
   [out] DWORD       *pccBufSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c86a5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c86a5-105">Parameters</span></span>  
 `pwzBuf`  
 <span data-ttu-id="c86a5-106">[out]バージョンを指定する文字列を格納する配列。</span><span class="sxs-lookup"><span data-stu-id="c86a5-106">[out] An array to store the string that specifies the version.</span></span>  
  
 `ccBufSize`  
 <span data-ttu-id="c86a5-107">[in]ワイド文字単位のサイズの`pwzBuf`配列。</span><span class="sxs-lookup"><span data-stu-id="c86a5-107">[in] The size, in wide characters, of the `pwzBuf` array.</span></span>  
  
 `pccBufSize`  
 <span data-ttu-id="c86a5-108">[out]返される、null 終端文字を含め、ワイド文字の数、`pwzBuf`配列。</span><span class="sxs-lookup"><span data-stu-id="c86a5-108">[out] The number of wide characters, including a null terminator, returned in the `pwzBuf` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c86a5-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="c86a5-109">Remarks</span></span>  
 <span data-ttu-id="c86a5-110">`GetVersionString`メソッドは、現在のメタデータ スコープのビルドのバージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="c86a5-110">The `GetVersionString` method gets the built-for version of the current metadata scope.</span></span> <span data-ttu-id="c86a5-111">スコープが保存されていないこと、ビルドのバージョンはありませんし、空の文字列が返されます。</span><span class="sxs-lookup"><span data-stu-id="c86a5-111">If the scope has never been saved, it will not have a built-for version, and an empty string will be returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c86a5-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="c86a5-112">Requirements</span></span>  
 <span data-ttu-id="c86a5-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c86a5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c86a5-114">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c86a5-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c86a5-115">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="c86a5-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c86a5-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c86a5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c86a5-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="c86a5-117">See also</span></span>

- [<span data-ttu-id="c86a5-118">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c86a5-118">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="c86a5-119">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c86a5-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
