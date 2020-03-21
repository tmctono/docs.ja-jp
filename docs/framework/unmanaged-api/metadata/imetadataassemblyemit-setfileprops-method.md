---
title: IMetaDataAssemblyEmit::SetFileProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetFileProps
helpviewer_keywords:
- IMetaDataAssemblyEmit::SetFileProps method [.NET Framework metadata]
- SetFileProps method [.NET Framework metadata]
ms.assetid: 85667d38-611c-45a9-938d-930ac7a7b681
topic_type:
- apiref
ms.openlocfilehash: 25baa6ffda3d50915cc7898275d6a557c1b3e947
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176033"
---
# <a name="imetadataassemblyemitsetfileprops-method"></a><span data-ttu-id="0362c-102">IMetaDataAssemblyEmit::SetFileProps メソッド</span><span class="sxs-lookup"><span data-stu-id="0362c-102">IMetaDataAssemblyEmit::SetFileProps Method</span></span>
<span data-ttu-id="0362c-103">指定された `File` メタデータ構造体を変更します。</span><span class="sxs-lookup"><span data-stu-id="0362c-103">Modifies the specified `File` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0362c-104">構文</span><span class="sxs-lookup"><span data-stu-id="0362c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0362c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0362c-105">Parameters</span></span>  
 `file`  
 <span data-ttu-id="0362c-106">[in]変更するメタデータ構造を`File`指定するメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="0362c-106">[in] The metadata token that specifies the `File` metadata structure to be modified.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="0362c-107">[in]ファイルに関連付けられているハッシュ データへのポインター。</span><span class="sxs-lookup"><span data-stu-id="0362c-107">[in] A pointer to the hash data associated with the file.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="0362c-108">[in]のサイズ (バイト`pbHashValue`単位)</span><span class="sxs-lookup"><span data-stu-id="0362c-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="0362c-109">[in]ファイルのさまざまな属性を指定する[CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md)値のビットごとの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="0362c-109">[in] A bitwise combination of [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values that specify various attributes of the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0362c-110">解説</span><span class="sxs-lookup"><span data-stu-id="0362c-110">Remarks</span></span>  
 <span data-ttu-id="0362c-111">メタデータ構造を`File`作成するには[、IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="0362c-111">To create a `File` metadata structure, use the [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0362c-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="0362c-112">Requirements</span></span>  
 <span data-ttu-id="0362c-113">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0362c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0362c-114">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="0362c-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0362c-115">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="0362c-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0362c-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0362c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0362c-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="0362c-117">See also</span></span>

- [<span data-ttu-id="0362c-118">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0362c-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
