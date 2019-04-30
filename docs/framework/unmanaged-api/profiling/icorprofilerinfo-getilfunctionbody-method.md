---
title: ICorProfilerInfo::GetILFunctionBody メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILFunctionBody
helpviewer_keywords:
- GetILFunctionBody method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBody method [.NET Framework profiling]
ms.assetid: e29b46bc-5fdc-4894-b0c2-619df4b65ded
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b2960bc0cfc39adb9b7cbca236d495baf630a173
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61991849"
---
# <a name="icorprofilerinfogetilfunctionbody-method"></a><span data-ttu-id="8c156-102">ICorProfilerInfo::GetILFunctionBody メソッド</span><span class="sxs-lookup"><span data-stu-id="8c156-102">ICorProfilerInfo::GetILFunctionBody Method</span></span>
<span data-ttu-id="8c156-103">開始位置のヘッダーとして、Microsoft intermediate language (MSIL) コードでメソッドの本体にポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="8c156-103">Gets a pointer to the body of a method in Microsoft intermediate language (MSIL) code, starting at its header.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c156-104">構文</span><span class="sxs-lookup"><span data-stu-id="8c156-104">Syntax</span></span>  
  
```  
HRESULT GetILFunctionBody(  
    [in]  ModuleID    moduleId,  
    [in]  mdMethodDef methodId,  
    [out] LPCBYTE     *ppMethodHeader,  
    [out] ULONG       *pcbMethodSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c156-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8c156-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="8c156-106">[in]関数が存在するモジュールの ID。</span><span class="sxs-lookup"><span data-stu-id="8c156-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodId`  
 <span data-ttu-id="8c156-107">[in]メソッドのメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="8c156-107">[in] The metadata token for the method.</span></span>  
  
 `ppMethodHeader`  
 <span data-ttu-id="8c156-108">[out]メソッドのヘッダーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8c156-108">[out] A pointer to the method's header.</span></span>  
  
 `pcbMethodSize`  
 <span data-ttu-id="8c156-109">[out]メソッドのサイズを指定する整数。</span><span class="sxs-lookup"><span data-stu-id="8c156-109">[out] An integer that specifies the size of the method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c156-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="8c156-110">Remarks</span></span>  
 <span data-ttu-id="8c156-111">メソッドは、中で、モジュールによって制限されます。</span><span class="sxs-lookup"><span data-stu-id="8c156-111">A method is scoped by the module in which it lives.</span></span> <span data-ttu-id="8c156-112">`GetILFunctionBody`メソッドが共通言語ランタイム (CLR) によって読み込まれている前に、MSIL コードをツールへのアクセスを付与するように設計、目的のインスタンスを検索するメソッドのメタデータ トークンを使用します。</span><span class="sxs-lookup"><span data-stu-id="8c156-112">Because the `GetILFunctionBody` method is designed to give a tool access to the MSIL code before it has been loaded by the common language runtime (CLR), it uses the metadata token of the method to find the desired instance.</span></span>  
  
 <span data-ttu-id="8c156-113">`GetILFunctionBody` CORPROF_E_FUNCTION_NOT_IL HRESULT を返す場合、`methodId`せず、任意の MSIL コード (など、抽象メソッドまたはプラットフォーム (PInvoke) のメソッドを呼び出す) メソッドを指します。</span><span class="sxs-lookup"><span data-stu-id="8c156-113">`GetILFunctionBody` can return a CORPROF_E_FUNCTION_NOT_IL HRESULT if the `methodId` points to a method without any MSIL code (such as an abstract method, or a platform invoke (PInvoke) method).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c156-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="8c156-114">Requirements</span></span>  
 <span data-ttu-id="8c156-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c156-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c156-116">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8c156-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8c156-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c156-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c156-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c156-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c156-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c156-119">See also</span></span>

- [<span data-ttu-id="8c156-120">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8c156-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
