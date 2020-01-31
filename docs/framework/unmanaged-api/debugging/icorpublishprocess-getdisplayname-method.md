---
title: ICorPublishProcess::GetDisplayName メソッド
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.GetDisplayName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::GetDisplayName
helpviewer_keywords:
- ICorPublishProcess::GetDisplayName method [.NET Framework debugging]
- GetDisplayName method, ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 7c0af9e9-a73f-41aa-a685-b21c439e059d
topic_type:
- apiref
ms.openlocfilehash: 7f2e644340a2ec7fe807830422b927ce811ddcf9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790574"
---
# <a name="icorpublishprocessgetdisplayname-method"></a><span data-ttu-id="147f8-102">ICorPublishProcess::GetDisplayName メソッド</span><span class="sxs-lookup"><span data-stu-id="147f8-102">ICorPublishProcess::GetDisplayName Method</span></span>
<span data-ttu-id="147f8-103">この[ICorPublishProcess](icorpublishprocess-interface.md)によって参照されるプロセスの実行可能ファイルの完全パスを取得します。</span><span class="sxs-lookup"><span data-stu-id="147f8-103">Gets the full path of the executable for the process referenced by this [ICorPublishProcess](icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="147f8-104">構文</span><span class="sxs-lookup"><span data-stu-id="147f8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDisplayName (  
    [in]  ULONG32                    cchName,   
    [out] ULONG32                    *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR                        *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="147f8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="147f8-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="147f8-106">[in] `szName` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="147f8-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="147f8-107">入出力`szName` 配列で返されるワイド文字数。</span><span class="sxs-lookup"><span data-stu-id="147f8-107">[out] The number of wide characters returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="147f8-108">入出力実行可能ファイルの完全パスを含む、名前を格納する配列。</span><span class="sxs-lookup"><span data-stu-id="147f8-108">[out] An array to store the name, including the full path, of the executable.</span></span> <span data-ttu-id="147f8-109">名前が null で終了しています。</span><span class="sxs-lookup"><span data-stu-id="147f8-109">The name is null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="147f8-110">要件</span><span class="sxs-lookup"><span data-stu-id="147f8-110">Requirements</span></span>  
 <span data-ttu-id="147f8-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="147f8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="147f8-112">**ヘッダー:** CorPub .idl、CorPub .h</span><span class="sxs-lookup"><span data-stu-id="147f8-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="147f8-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="147f8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="147f8-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="147f8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="147f8-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="147f8-115">See also</span></span>

- [<span data-ttu-id="147f8-116">ICorPublishProcess インターフェイス</span><span class="sxs-lookup"><span data-stu-id="147f8-116">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
