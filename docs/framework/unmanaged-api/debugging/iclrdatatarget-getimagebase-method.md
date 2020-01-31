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
ms.openlocfilehash: fcf0ab73c79a5fa116a89cdfcc2e73b17d9eabfc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785491"
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="48a14-102">ICLRDataTarget::GetImageBase メソッド</span><span class="sxs-lookup"><span data-stu-id="48a14-102">ICLRDataTarget::GetImageBase Method</span></span>
<span data-ttu-id="48a14-103">指定したイメージのベースメモリアドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="48a14-103">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48a14-104">構文</span><span class="sxs-lookup"><span data-stu-id="48a14-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48a14-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="48a14-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="48a14-106">からパスを含む、イメージのファイル名。</span><span class="sxs-lookup"><span data-stu-id="48a14-106">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="48a14-107">入出力イメージのベースアドレスを格納する CLRDATA_ADDRESS へのポインター。</span><span class="sxs-lookup"><span data-stu-id="48a14-107">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48a14-108">コメント</span><span class="sxs-lookup"><span data-stu-id="48a14-108">Remarks</span></span>  
 <span data-ttu-id="48a14-109">イメージファイル名には、パスを指定することも、パスを指定することもできません。</span><span class="sxs-lookup"><span data-stu-id="48a14-109">The image file name may or may not have a path.</span></span> <span data-ttu-id="48a14-110">パスが指定されている場合、パス全体で一致が行われます。それ以外の場合、一致はファイル名でのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="48a14-110">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48a14-111">要件</span><span class="sxs-lookup"><span data-stu-id="48a14-111">Requirements</span></span>  
 <span data-ttu-id="48a14-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48a14-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48a14-113">**ヘッダー:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="48a14-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="48a14-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48a14-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48a14-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48a14-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48a14-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="48a14-116">See also</span></span>

- [<span data-ttu-id="48a14-117">ICLRDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="48a14-117">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
