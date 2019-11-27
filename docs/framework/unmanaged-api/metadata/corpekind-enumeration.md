---
title: CorPEKind 列挙型
ms.date: 03/30/2017
api_name:
- CorPEKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPEKind
helpviewer_keywords:
- CorPEKind enumeration [.NET Framework metadata]
ms.assetid: 22dc6dea-b1b9-4982-a730-a022d586b117
topic_type:
- apiref
ms.openlocfilehash: 74670a1477546066145bd4bbf2f123a252e10b55
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436476"
---
# <a name="corpekind-enumeration"></a><span data-ttu-id="b1b8c-102">CorPEKind 列挙型</span><span class="sxs-lookup"><span data-stu-id="b1b8c-102">CorPEKind Enumeration</span></span>
<span data-ttu-id="b1b8c-103">[IMetaDataImport2:: GetPEKind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)の呼び出しから返される、ポータブル実行可能 (PE) ファイルを記述する値を格納します。</span><span class="sxs-lookup"><span data-stu-id="b1b8c-103">Contains values that describe a portable executable (PE) file, as returned from a call to [IMetaDataImport2::GetPEKind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1b8c-104">構文</span><span class="sxs-lookup"><span data-stu-id="b1b8c-104">Syntax</span></span>  
  
```cpp  
typedef enum CorPEKind {  
  
    peNot           = 0x00000000,  
    peILonly        = 0x00000001,  
    pe32BitRequired = 0x00000002,  
    pe32Plus        = 0x00000004,  
    pe32Unmanaged   = 0x00000008,  
    pe32BitPreferred= 0x00000010  
  
} CorPEKind;  
```  
  
## <a name="members"></a><span data-ttu-id="b1b8c-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="b1b8c-105">Members</span></span>  
  
|<span data-ttu-id="b1b8c-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="b1b8c-106">Member</span></span>|<span data-ttu-id="b1b8c-107">説明</span><span class="sxs-lookup"><span data-stu-id="b1b8c-107">Description</span></span>|  
|------------|-----------------|  
|`peNot`|<span data-ttu-id="b1b8c-108">これが PE ファイルではないことを示します。</span><span class="sxs-lookup"><span data-stu-id="b1b8c-108">Indicates that this is not a PE file.</span></span>|  
|`peILOnly`|<span data-ttu-id="b1b8c-109">この PE ファイルにマネージコードのみが含まれていることを示します。</span><span class="sxs-lookup"><span data-stu-id="b1b8c-109">Indicates that this PE file contains only managed code.</span></span>|  
|`pe32BitRequired`|<span data-ttu-id="b1b8c-110">この PE ファイルが Win32 呼び出しを行うことを示します。</span><span class="sxs-lookup"><span data-stu-id="b1b8c-110">Indicates that this PE file makes Win32 calls.</span></span>|  
|`pe32Plus`|<span data-ttu-id="b1b8c-111">この PE ファイルが64ビットプラットフォームで実行されることを示します。</span><span class="sxs-lookup"><span data-stu-id="b1b8c-111">Indicates that this PE file runs on a 64-bit platform.</span></span>|  
|`pe32Unmanaged`|<span data-ttu-id="b1b8c-112">この PE ファイルがネイティブコードであることを示します。</span><span class="sxs-lookup"><span data-stu-id="b1b8c-112">Indicates that this PE file is native code.</span></span>|  
|<span data-ttu-id="b1b8c-113">pe32BitPreferred</span><span class="sxs-lookup"><span data-stu-id="b1b8c-113">pe32BitPreferred</span></span>|<span data-ttu-id="b1b8c-114">この PE ファイルがプラットフォームに依存せず、32ビット環境で読み込まれることを示すことを示します。</span><span class="sxs-lookup"><span data-stu-id="b1b8c-114">Indicates that this PE file is platform-neutral and prefers to be loaded in a 32-bit environment.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b1b8c-115">コメント</span><span class="sxs-lookup"><span data-stu-id="b1b8c-115">Remarks</span></span>  
 <span data-ttu-id="b1b8c-116">これらの値は、ビットごとの組み合わせで使用できます。</span><span class="sxs-lookup"><span data-stu-id="b1b8c-116">These values can be used in bitwise combinations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1b8c-117">要件</span><span class="sxs-lookup"><span data-stu-id="b1b8c-117">Requirements</span></span>  
 <span data-ttu-id="b1b8c-118">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1b8c-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1b8c-119">**ヘッダー:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="b1b8c-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="b1b8c-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1b8c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1b8c-121">参照</span><span class="sxs-lookup"><span data-stu-id="b1b8c-121">See also</span></span>

- [<span data-ttu-id="b1b8c-122">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="b1b8c-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
