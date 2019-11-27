---
title: IMetaDataAssemblyEmit::SetAssemblyProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyProps method [.NET Framework metadata]
ms.assetid: 91b633d7-9e75-43c3-a8d2-2144984e5f9e
topic_type:
- apiref
ms.openlocfilehash: f79320d5b7d2ad4ad44a79fae063ce6718490a70
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431953"
---
# <a name="imetadataassemblyemitsetassemblyprops-method"></a><span data-ttu-id="7d6fe-102">IMetaDataAssemblyEmit::SetAssemblyProps メソッド</span><span class="sxs-lookup"><span data-stu-id="7d6fe-102">IMetaDataAssemblyEmit::SetAssemblyProps Method</span></span>
<span data-ttu-id="7d6fe-103">指定された `Assembly` メタデータ構造体を変更します。</span><span class="sxs-lookup"><span data-stu-id="7d6fe-103">Modifies the specified `Assembly` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d6fe-104">構文</span><span class="sxs-lookup"><span data-stu-id="7d6fe-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyProps (  
    [in] mdAssembly               pma,  
    [in] const void               *pbPublicKey,  
    [in] ULONG                    cbPublicKey,  
    [in] ULONG                    ulHashAlgId,  
    [in] LPCWSTR                  szName,  
    [in] const ASSEMBLYMETADATA   *pMetaData,  
    [in] DWORD                    dwAssemblyFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d6fe-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7d6fe-105">Parameters</span></span>  
 `pma`  
 <span data-ttu-id="7d6fe-106">から変更する `Assembly` メタデータ構造を指定するメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="7d6fe-106">[in] The metadata token that specifies the `Assembly` metadata structure to be modified.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="7d6fe-107">からアセンブリの発行者の公開キーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="7d6fe-107">[in] A pointer to the public key of the publisher of the assembly.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="7d6fe-108">から`pbPublicKey`のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="7d6fe-108">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `ulHashAlgId`  
 <span data-ttu-id="7d6fe-109">からアセンブリファイルのハッシュに使用されるハッシュアルゴリズムの識別子。</span><span class="sxs-lookup"><span data-stu-id="7d6fe-109">[in] The identifier for the hash algorithm used to hash the assembly files.</span></span>  
  
 `szName`  
 <span data-ttu-id="7d6fe-110">からユーザーが判読できる、アセンブリのテキスト名。</span><span class="sxs-lookup"><span data-stu-id="7d6fe-110">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="7d6fe-111">からアセンブリのバージョン、プラットフォーム、およびロケール情報を格納している ASSEMBLYMETADATA へのポインター。</span><span class="sxs-lookup"><span data-stu-id="7d6fe-111">[in] A pointer to the ASSEMBLYMETADATA that contains version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="7d6fe-112">からアセンブリのさまざまな属性を指定する[Assemblyflags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md)値のビットごとの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="7d6fe-112">[in] A bitwise combination of [AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md) values that specify various attributes of the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d6fe-113">コメント</span><span class="sxs-lookup"><span data-stu-id="7d6fe-113">Remarks</span></span>  
 <span data-ttu-id="7d6fe-114">`Assembly` メタデータ構造を作成するには、 [IMetaDataAssemblyEmit::D efineAssembly](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md)メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="7d6fe-114">To create an `Assembly` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssembly](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d6fe-115">要件</span><span class="sxs-lookup"><span data-stu-id="7d6fe-115">Requirements</span></span>  
 <span data-ttu-id="7d6fe-116">**プラットフォーム:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d6fe-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d6fe-117">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="7d6fe-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7d6fe-118">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="7d6fe-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7d6fe-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d6fe-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d6fe-120">参照</span><span class="sxs-lookup"><span data-stu-id="7d6fe-120">See also</span></span>

- [<span data-ttu-id="7d6fe-121">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7d6fe-121">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
