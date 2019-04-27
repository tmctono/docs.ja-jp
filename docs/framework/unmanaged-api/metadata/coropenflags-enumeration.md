---
title: CorOpenFlags 列挙型
ms.date: 03/30/2017
api_name:
- CorOpenFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorOpenFlags
helpviewer_keywords:
- CorOpenFlags enumeration [.NET Framework metadata]
ms.assetid: e27a83b5-2698-4996-9032-1e0fed8b91ca
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 55934ef08b10764bb705d7c166621ec7cfcadd0a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992681"
---
# <a name="coropenflags-enumeration"></a><span data-ttu-id="cfe2d-102">CorOpenFlags 列挙型</span><span class="sxs-lookup"><span data-stu-id="cfe2d-102">CorOpenFlags Enumeration</span></span>
<span data-ttu-id="cfe2d-103">マニフェスト ファイルを開くときにメタデータの動作を制御するフラグ値を含めます。</span><span class="sxs-lookup"><span data-stu-id="cfe2d-103">Contains flag values that control metadata behavior upon opening manifest files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfe2d-104">構文</span><span class="sxs-lookup"><span data-stu-id="cfe2d-104">Syntax</span></span>  
  
```  
typedef enum CorOpenFlags  
{  
    ofRead              =   0x00000000,  
    ofWrite             =   0x00000001,  
    ofReadWriteMask     =   0x00000001,  
    ofCopyMemory        =   0x00000002,  
    ofCacheImage        =   0x00000004,  
    ofManifestMetadata  =   0x00000008,  
    ofReadOnly          =   0x00000010,  
    ofTakeOwnership     =   0x00000020,  
    ofCacheImage        =   0x00000004,  
    ofNoTypeLib         =   0x00000080,  
    ofNoTransform       =   0x00001000,  
    ofReserved1         =   0x00000100,  
    ofReserved2         =   0x00000200,  
    ofReserved          =   0xffffff40  
} CorOpenFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="cfe2d-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="cfe2d-105">Members</span></span>  
  
|<span data-ttu-id="cfe2d-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="cfe2d-106">Member</span></span>|<span data-ttu-id="cfe2d-107">説明</span><span class="sxs-lookup"><span data-stu-id="cfe2d-107">Description</span></span>|  
|------------|-----------------|  
|`ofRead`|<span data-ttu-id="cfe2d-108">ファイルが読み取り専用で開かれることを示します。</span><span class="sxs-lookup"><span data-stu-id="cfe2d-108">Indicates that the file should be opened for reading only.</span></span>|  
|`ofWrite`|<span data-ttu-id="cfe2d-109">ファイルが書き込み用に開かれることを示します。</span><span class="sxs-lookup"><span data-stu-id="cfe2d-109">Indicates that the file should be opened for writing.</span></span><br /><br /> <span data-ttu-id="cfe2d-110">.winmd ファイルを開くときに `ofWrite` フラグを使用する場合は、`ofNoTransform` フラグも渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfe2d-110">If you are using the `ofWrite` flag when opening a .winmd file, you should also pass the `ofNoTransform` flag.</span></span>|  
|`ofReadWriteMask`|<span data-ttu-id="cfe2d-111">読み取りおよび書き込み用のマスク。</span><span class="sxs-lookup"><span data-stu-id="cfe2d-111">A mask for reading and writing.</span></span>|  
|`ofCopyMemory`|<span data-ttu-id="cfe2d-112">ファイルがメモリ内に読み込まれることを示します。</span><span class="sxs-lookup"><span data-stu-id="cfe2d-112">Indicates that the file should be read into memory.</span></span> <span data-ttu-id="cfe2d-113">メタデータは自身のコピーを保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfe2d-113">Metadata should maintain its own copy.</span></span>|  
|`ofCacheImage`|<span data-ttu-id="cfe2d-114">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="cfe2d-114">Obsolete.</span></span> <span data-ttu-id="cfe2d-115">このフラグは無視されます。</span><span class="sxs-lookup"><span data-stu-id="cfe2d-115">This flag is ignored.</span></span>|  
|`ofManifestMetadata`|<span data-ttu-id="cfe2d-116">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="cfe2d-116">Obsolete.</span></span> <span data-ttu-id="cfe2d-117">このフラグは無視されます。</span><span class="sxs-lookup"><span data-stu-id="cfe2d-117">This flag is ignored.</span></span>|  
|`ofReadOnly`|<span data-ttu-id="cfe2d-118">読み取り用にファイルが開かれることを示しますへの呼び出し`QueryInterface`の[IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)にことはできません。</span><span class="sxs-lookup"><span data-stu-id="cfe2d-118">Indicates that the file should be opened for reading, and that a call to `QueryInterface` for an [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) cannot be made.</span></span>|  
|`ofTakeOwnership`|<span data-ttu-id="cfe2d-119">呼び出しを使用してメモリが割り当てられたことを示します[CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc)メタデータによって解放されるとします。</span><span class="sxs-lookup"><span data-stu-id="cfe2d-119">Indicates that the memory was allocated using a call to [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) and will be freed by the metadata.</span></span>|  
|`ofNoTypeLib`|<span data-ttu-id="cfe2d-120">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="cfe2d-120">Obsolete.</span></span> <span data-ttu-id="cfe2d-121">このフラグは無視されます。</span><span class="sxs-lookup"><span data-stu-id="cfe2d-121">This flag is ignored.</span></span>|  
|`ofNoTransform`|<span data-ttu-id="cfe2d-122">.winmd ファイルの自動変換を無効にする必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="cfe2d-122">Indicates that automatic transforms of .winmd files should be disabled.</span></span> <span data-ttu-id="cfe2d-123">つまり、Windows Runtime タイプから .NET Framework タイプへの投射は無効になります。</span><span class="sxs-lookup"><span data-stu-id="cfe2d-123">In other words, the projection of a Windows Runtime type to a .NET Framework type should be disabled.</span></span> <span data-ttu-id="cfe2d-124">詳細については、次を参照してください。 [Windows ランタイムと CLR の内部での .NET and Windows Runtime](https://msdn.microsoft.com/magazine/jj651569.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="cfe2d-124">For more information, see [Windows Runtime and the CLR - Underneath the Hood with .NET and the Windows Runtime](https://msdn.microsoft.com/magazine/jj651569.aspx).</span></span>|  
|`ofReserved1`|<span data-ttu-id="cfe2d-125">内部使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="cfe2d-125">Reserved for internal use.</span></span>|  
|`ofReserved2`|<span data-ttu-id="cfe2d-126">内部使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="cfe2d-126">Reserved for internal use.</span></span>|  
|`ofReserved`|<span data-ttu-id="cfe2d-127">内部使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="cfe2d-127">Reserved for internal use.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cfe2d-128">必要条件</span><span class="sxs-lookup"><span data-stu-id="cfe2d-128">Requirements</span></span>  
 <span data-ttu-id="cfe2d-129">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfe2d-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfe2d-130">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="cfe2d-130">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="cfe2d-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfe2d-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfe2d-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="cfe2d-132">See also</span></span>

- [<span data-ttu-id="cfe2d-133">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="cfe2d-133">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
