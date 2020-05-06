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
ms.openlocfilehash: 71b07e11cd3fec1a0dbebe986d98067c2e6f18e1
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860631"
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="7e434-102">ICLRDataTarget::GetImageBase メソッド</span><span class="sxs-lookup"><span data-stu-id="7e434-102">ICLRDataTarget::GetImageBase Method</span></span>
<span data-ttu-id="7e434-103">指定したイメージのベースメモリアドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="7e434-103">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e434-104">構文</span><span class="sxs-lookup"><span data-stu-id="7e434-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e434-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7e434-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="7e434-106">からパスを含む、イメージのファイル名。</span><span class="sxs-lookup"><span data-stu-id="7e434-106">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="7e434-107">入出力イメージのベースアドレスを格納する CLRDATA_ADDRESS へのポインター。</span><span class="sxs-lookup"><span data-stu-id="7e434-107">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e434-108">解説</span><span class="sxs-lookup"><span data-stu-id="7e434-108">Remarks</span></span>  
 <span data-ttu-id="7e434-109">イメージファイル名には、パスを指定することも、パスを指定することもできません。</span><span class="sxs-lookup"><span data-stu-id="7e434-109">The image file name may or may not have a path.</span></span> <span data-ttu-id="7e434-110">パスが指定されている場合、パス全体で一致が行われます。それ以外の場合、一致はファイル名でのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="7e434-110">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e434-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="7e434-111">Requirements</span></span>  
 <span data-ttu-id="7e434-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e434-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e434-113">**ヘッダー:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="7e434-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="7e434-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e434-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7e434-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e434-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e434-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="7e434-116">See also</span></span>

- [<span data-ttu-id="7e434-117">ICLRDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7e434-117">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
