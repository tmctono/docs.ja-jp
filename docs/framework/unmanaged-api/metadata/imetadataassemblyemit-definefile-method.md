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
ms.openlocfilehash: 61d81c94e3a9c092b5d45791962635c761e8da8a
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008145"
---
# <a name="imetadataassemblyemitdefinefile-method"></a><span data-ttu-id="05930-102">IMetaDataAssemblyEmit::DefineFile メソッド</span><span class="sxs-lookup"><span data-stu-id="05930-102">IMetaDataAssemblyEmit::DefineFile Method</span></span>
<span data-ttu-id="05930-103">このアセンブリが参照するアセンブリのメタデータを含む `File` メタデータ構造体を作成し、関連付けられたメタデータ トークンを返します。</span><span class="sxs-lookup"><span data-stu-id="05930-103">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05930-104">構文</span><span class="sxs-lookup"><span data-stu-id="05930-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineFile (  
    [in]  LPCWSTR        szName,
    [in]  const void     *pbHashValue,
    [in]  ULONG          cbHashValue,  
    [in]  DWORD          dwFileFlags,  
    [out] mdFile         *pmdf  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05930-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="05930-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="05930-106">から使用するファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="05930-106">[in] The name of the file to be consumed.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="05930-107">からアセンブリに関連付けられているハッシュデータへのポインター。</span><span class="sxs-lookup"><span data-stu-id="05930-107">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="05930-108">からのサイズ (バイト単位) `pbHashValue` 。</span><span class="sxs-lookup"><span data-stu-id="05930-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="05930-109">から`FileFlags`プロパティ設定を指定する値のビットごとの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="05930-109">[in] A bitwise combination of `FileFlags` values that specify property settings.</span></span>  
  
 `pmdf`  
 <span data-ttu-id="05930-110">入出力返されたトークンへのポインター `File` 。</span><span class="sxs-lookup"><span data-stu-id="05930-110">[out] A pointer to the returned `File` token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05930-111">コメント</span><span class="sxs-lookup"><span data-stu-id="05930-111">Remarks</span></span>  
 <span data-ttu-id="05930-112">このアセンブリがビルドされた時点 `File` で、このアセンブリに含まれていたファイルごとに1つのメタデータ構造を定義する必要があります。メタデータを含むファイルは除きます。</span><span class="sxs-lookup"><span data-stu-id="05930-112">One `File` metadata structure must be defined for each file that was part of this assembly at the time that this assembly was built, excluding the file that contains the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05930-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="05930-113">Requirements</span></span>  
 <span data-ttu-id="05930-114">**プラットフォーム:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05930-114">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05930-115">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="05930-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="05930-116">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="05930-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="05930-117">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05930-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05930-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="05930-118">See also</span></span>

- [<span data-ttu-id="05930-119">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="05930-119">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
