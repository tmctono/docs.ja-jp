---
title: ICLRDataTarget::GetImageBase メソッド
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetImageBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetImageBase
helpviewer_keywords:
- ICLRDataTarget::GetImageBase method [.NET Framework debugging]
- GetImageBase method [.NET Framework debugging]
ms.assetid: 091c5f32-c160-49e3-a75f-4692e084c8e4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 91d893c0df13fbcb44c66df7f268cffdffb5fff6
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57488424"
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="15486-102">ICLRDataTarget::GetImageBase メソッド</span><span class="sxs-lookup"><span data-stu-id="15486-102">ICLRDataTarget::GetImageBase Method</span></span>
<span data-ttu-id="15486-103">指定したイメージのメモリのベース アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="15486-103">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15486-104">構文</span><span class="sxs-lookup"><span data-stu-id="15486-104">Syntax</span></span>  
  
```  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15486-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="15486-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="15486-106">[in]そのパスを含む、イメージのファイル名。</span><span class="sxs-lookup"><span data-stu-id="15486-106">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="15486-107">[out]イメージのベース アドレスを格納する CLRDATA_ADDRESS へのポインター。</span><span class="sxs-lookup"><span data-stu-id="15486-107">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15486-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="15486-108">Remarks</span></span>  
 <span data-ttu-id="15486-109">イメージのファイル名では、可能性がありますか、パスがない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="15486-109">The image file name may or may not have a path.</span></span> <span data-ttu-id="15486-110">照合はパス全体で行われますパスが指定されている場合それ以外の場合、照合はファイル名でのみ行われます。</span><span class="sxs-lookup"><span data-stu-id="15486-110">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15486-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="15486-111">Requirements</span></span>  
 <span data-ttu-id="15486-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="15486-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15486-113">**ヘッダー:** ClrData.idl、ClrData.h</span><span class="sxs-lookup"><span data-stu-id="15486-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="15486-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15486-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15486-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15486-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15486-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="15486-116">See also</span></span>
- [<span data-ttu-id="15486-117">ICLRDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="15486-117">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
