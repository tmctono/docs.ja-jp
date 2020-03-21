---
title: IMetaDataAssemblyEmit::DefineFile メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineFile
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineFile method [.NET Framework metadata]
- DefineFile method [.NET Framework metadata]
ms.assetid: c065aadf-c1ca-4981-bde6-597042cb29c4
topic_type:
- apiref
ms.openlocfilehash: cabd6a47e5d6fc2a4cea87b16d349d9c778b3507
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176059"
---
# <a name="imetadataassemblyemitdefinefile-method"></a><span data-ttu-id="447aa-102">IMetaDataAssemblyEmit::DefineFile メソッド</span><span class="sxs-lookup"><span data-stu-id="447aa-102">IMetaDataAssemblyEmit::DefineFile Method</span></span>
<span data-ttu-id="447aa-103">このアセンブリが参照するアセンブリのメタデータを含む `File` メタデータ構造体を作成し、関連付けられたメタデータ トークンを返します。</span><span class="sxs-lookup"><span data-stu-id="447aa-103">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="447aa-104">構文</span><span class="sxs-lookup"><span data-stu-id="447aa-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineFile (  
    [in]  LPCWSTR        szName,
    [in]  const void     *pbHashValue,
    [in]  ULONG          cbHashValue,  
    [in]  DWORD          dwFileFlags,  
    [out] mdFile         *pmdf  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="447aa-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="447aa-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="447aa-106">[in]使用するファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="447aa-106">[in] The name of the file to be consumed.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="447aa-107">[in]アセンブリに関連付けられているハッシュ データへのポインター。</span><span class="sxs-lookup"><span data-stu-id="447aa-107">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="447aa-108">[in]のサイズ (バイト`pbHashValue`単位)</span><span class="sxs-lookup"><span data-stu-id="447aa-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="447aa-109">[in]プロパティ設定を指定する`FileFlags`値のビットごとの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="447aa-109">[in] A bitwise combination of `FileFlags` values that specify property settings.</span></span>  
  
 `pmdf`  
 <span data-ttu-id="447aa-110">[アウト]返された`File`トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="447aa-110">[out] A pointer to the returned `File` token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="447aa-111">解説</span><span class="sxs-lookup"><span data-stu-id="447aa-111">Remarks</span></span>  
 <span data-ttu-id="447aa-112">この`File`アセンブリのビルド時にこのアセンブリの一部であったファイルごとに、メタデータを含むファイルを除いて、1 つのメタデータ構造を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="447aa-112">One `File` metadata structure must be defined for each file that was part of this assembly at the time that this assembly was built, excluding the file that contains the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="447aa-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="447aa-113">Requirements</span></span>  
 <span data-ttu-id="447aa-114">**プラットフォーム:**[「システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="447aa-114">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="447aa-115">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="447aa-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="447aa-116">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="447aa-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="447aa-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="447aa-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="447aa-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="447aa-118">See also</span></span>

- [<span data-ttu-id="447aa-119">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="447aa-119">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
