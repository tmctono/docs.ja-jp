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
ms.openlocfilehash: 8b6eab8156f72847eb6dd3369950f9b46a3fc877
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007560"
---
# <a name="corpekind-enumeration"></a><span data-ttu-id="bfea0-102">CorPEKind 列挙型</span><span class="sxs-lookup"><span data-stu-id="bfea0-102">CorPEKind Enumeration</span></span>
<span data-ttu-id="bfea0-103">[IMetaDataImport2:: GetPEKind](imetadataimport2-getpekind-method.md)の呼び出しから返される、ポータブル実行可能 (PE) ファイルを記述する値を格納します。</span><span class="sxs-lookup"><span data-stu-id="bfea0-103">Contains values that describe a portable executable (PE) file, as returned from a call to [IMetaDataImport2::GetPEKind](imetadataimport2-getpekind-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfea0-104">構文</span><span class="sxs-lookup"><span data-stu-id="bfea0-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="bfea0-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="bfea0-105">Members</span></span>  
  
|<span data-ttu-id="bfea0-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="bfea0-106">Member</span></span>|<span data-ttu-id="bfea0-107">説明</span><span class="sxs-lookup"><span data-stu-id="bfea0-107">Description</span></span>|  
|------------|-----------------|  
|`peNot`|<span data-ttu-id="bfea0-108">これが PE ファイルではないことを示します。</span><span class="sxs-lookup"><span data-stu-id="bfea0-108">Indicates that this is not a PE file.</span></span>|  
|`peILOnly`|<span data-ttu-id="bfea0-109">この PE ファイルにマネージコードのみが含まれていることを示します。</span><span class="sxs-lookup"><span data-stu-id="bfea0-109">Indicates that this PE file contains only managed code.</span></span>|  
|`pe32BitRequired`|<span data-ttu-id="bfea0-110">この PE ファイルが Win32 呼び出しを行うことを示します。</span><span class="sxs-lookup"><span data-stu-id="bfea0-110">Indicates that this PE file makes Win32 calls.</span></span>|  
|`pe32Plus`|<span data-ttu-id="bfea0-111">この PE ファイルが64ビットプラットフォームで実行されることを示します。</span><span class="sxs-lookup"><span data-stu-id="bfea0-111">Indicates that this PE file runs on a 64-bit platform.</span></span>|  
|`pe32Unmanaged`|<span data-ttu-id="bfea0-112">この PE ファイルがネイティブコードであることを示します。</span><span class="sxs-lookup"><span data-stu-id="bfea0-112">Indicates that this PE file is native code.</span></span>|  
|<span data-ttu-id="bfea0-113">pe32BitPreferred</span><span class="sxs-lookup"><span data-stu-id="bfea0-113">pe32BitPreferred</span></span>|<span data-ttu-id="bfea0-114">この PE ファイルがプラットフォームに依存せず、32ビット環境で読み込まれることを示すことを示します。</span><span class="sxs-lookup"><span data-stu-id="bfea0-114">Indicates that this PE file is platform-neutral and prefers to be loaded in a 32-bit environment.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bfea0-115">コメント</span><span class="sxs-lookup"><span data-stu-id="bfea0-115">Remarks</span></span>  
 <span data-ttu-id="bfea0-116">これらの値は、ビットごとの組み合わせで使用できます。</span><span class="sxs-lookup"><span data-stu-id="bfea0-116">These values can be used in bitwise combinations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfea0-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="bfea0-117">Requirements</span></span>  
 <span data-ttu-id="bfea0-118">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfea0-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfea0-119">**ヘッダー:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="bfea0-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="bfea0-120">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfea0-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfea0-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="bfea0-121">See also</span></span>

- [<span data-ttu-id="bfea0-122">メタデータ列挙体</span><span class="sxs-lookup"><span data-stu-id="bfea0-122">Metadata Enumerations</span></span>](metadata-enumerations.md)
