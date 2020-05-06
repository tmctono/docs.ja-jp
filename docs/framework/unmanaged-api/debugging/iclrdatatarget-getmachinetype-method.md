---
title: ICLRDataTarget::GetMachineType メソッド
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetMachineType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetMachineType
helpviewer_keywords:
- ICLRDataTarget::GetMachineType method [.NET Framework debugging]
- GetMachineType method [.NET Framework debugging]
ms.assetid: 5f1f9c61-3e3b-48b2-b111-a4395f7623a7
topic_type:
- apiref
ms.openlocfilehash: 9d86b23b91702929a86334f557a8d647e19861a4
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860597"
---
# <a name="iclrdatatargetgetmachinetype-method"></a><span data-ttu-id="42ad0-102">ICLRDataTarget::GetMachineType メソッド</span><span class="sxs-lookup"><span data-stu-id="42ad0-102">ICLRDataTarget::GetMachineType Method</span></span>
<span data-ttu-id="42ad0-103">ターゲットプロセスが使用している命令セットの種類の識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="42ad0-103">Gets the identifier for the kind of instruction set that the target process is using.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42ad0-104">構文</span><span class="sxs-lookup"><span data-stu-id="42ad0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMachineType (  
    [out] ULONG32     *machineType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42ad0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="42ad0-105">Parameters</span></span>  
 `machineType`  
 <span data-ttu-id="42ad0-106">入出力ターゲットプロセスが使用している命令セットを示す値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="42ad0-106">[out] A pointer to a value that indicates the instruction set that the target process is using.</span></span> <span data-ttu-id="42ad0-107">返さ`machineType`れるは、winnt.h ヘッダーファイルで定義されている IMAGE_FILE_MACHINE 定数の1つです。</span><span class="sxs-lookup"><span data-stu-id="42ad0-107">The returned `machineType` is one of the IMAGE_FILE_MACHINE constants, which are defined in the WinNT.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42ad0-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="42ad0-108">Requirements</span></span>  
 <span data-ttu-id="42ad0-109">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42ad0-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42ad0-110">**ヘッダー:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="42ad0-110">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="42ad0-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42ad0-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42ad0-112">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42ad0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42ad0-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="42ad0-113">See also</span></span>

- [<span data-ttu-id="42ad0-114">ICLRDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="42ad0-114">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
