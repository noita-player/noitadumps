AIAttackComponent
 - Members -----------------------------
    use_probability                                                 100 [0, 100]                    "The probability for using this attack if it's otherwise possible"
    min_distance                                                    10 [0, 10000]                   "The minimum distance from enemy at which we can perform this attack."
    max_distance                                                    160 [0, 10000]                  "The maximum distance from enemy at which we can perform this attack."
    angular_range_deg                                               90 [0, 90]                      "When looking for threats/prey this is our field of view around the X axis. 90 means we scan the whole 180 degrees around the X axis, to the left and right."
    state_duration_frames                                           45 [0, 1000]                    "How long do we stay in the attack state, before other states are allowed?"
    frames_between                                                  180 [0, 1000]                   "The minimum number of frames we wait between these attacks"
    frames_between_global                                           30 [0, 1000]                    "The minimum number of frames we wait after this attack before doing any other ranged attack"
    animation_name                                                  attack_ranged [0, 1]            "The animation to play when performing this attack"
    attack_landing_ranged_enabled                                   0 [0, 1]                        "If 1, we try to land before doing the attack, if there's ground near nearby under us"
    attack_ranged_action_frame                                      2 [0, 1000]                     "The frame of the 'attack_ranged' animation during which the ranged attack actually occurs"
    attack_ranged_offset_x                                          0 [-1000, 1000]                 "'attack_ranged_entity_file' is created here when performing a ranged attack"
    attack_ranged_offset_y                                          0 [-1000, 1000]                 "'attack_ranged_entity_file' is created here when performing a ranged attack"
    attack_ranged_root_offset_x                                     0 [-1000, 1000]                 ""
    attack_ranged_root_offset_y                                     0 [-1000, 1000]                 ""
    attack_ranged_use_message                                       0 [0, 1]                        "If 1, we do ranged attacks by sending a Message_UseItem"
    attack_ranged_predict                                           0 [0, 1]                        "If 1, we attempt to predict target movement and shoot accordingly"
    attack_ranged_entity_file                                       data/entities/projectiles/spear.xml [0, 1] "File to projectile entity that is created when performing a ranged attack"
    attack_ranged_entity_count_min                                  1 [0, 1000]                     "Minimum number of projectiles shot when performing a ranged attack"
    attack_ranged_entity_count_max                                  1 [0, 1000]                     "Maximum number of projectiles shot when performing a ranged attack"
    attack_ranged_use_laser_sight                                   0 [0, 1]                        "If 1, we draw a laser sight to our target. Requires entity to have a sprite with tag 'laser_sight'"
    attack_ranged_aim_rotation_enabled                              0 [0, 1]                        "If 1, we use a laser sight"
    attack_ranged_aim_rotation_speed                                3 [0, 1]                        "How fast can we rotate our aim to track targets"
    attack_ranged_aim_rotation_shooting_ok_angle_deg                10 [0, 1]                       "If our aim is closer than this to the target we shoot"
 - Privates -----------------------------
    mRangedAttackCurrentAimAngle                                    0 [0, 1]                        "which direction does our gun currently point at, physically saying?"
    mNextFrameUsable                                                0 [0, 1]                        ""

AIComponent
 - Members -----------------------------
    TEMP_TEMP_TEMP                                                  0 [0, 3.5]                      ""
 - Privates -----------------------------
    data                                                            -                               ""

AbilityComponent
 - Members -----------------------------
    cooldown_frames                                                 0 [0, 60000]                    ""
    entity_file                                                     -                               "the projectile entity file"
    sprite_file                                                     -                               ""
    entity_count                                                    1 [0, 60000]                    ""
    never_reload                                                    0 [0, 1]                        ""
    reload_time_frames                                              0 [0, 1]                        ""
    mana                                                            0 [0, 1]                        ""
    mana_max                                                        100 [0, 1]                      ""
    mana_charge_speed                                               10 [0, 1]                       ""
    rotate_in_hand                                                  1 [0, 1]                        ""
    rotate_in_hand_amount                                           1 [0, 1]                        "[0-1], how much does the item rotate related to the actual aiming angle"
    rotate_hand_amount                                              0.7 [0, 1]                      "[0-1], how much does hand sprite rotate related to the actual aiming angle"
    fast_projectile                                                 0 [0, 1]                        "if 1, then the velocity of the bullet is increased quite a bit. Lightning requires this"
    swim_propel_amount                                              0 [-1000, 1000]                 ""
    max_charged_actions                                             0 [0, 1]                        ""
    charge_wait_frames                                              10 [0, 1]                       ""
    item_recoil_recovery_speed                                      15 [0, 1]                       "How quickly does the item return to resting state after getting recoil"
    item_recoil_max                                                 1 [0, 1]                        "Maximum distance moved by recoil"
    item_recoil_offset_coeff                                        1 [0, 1]                        "Item distance moved by recoil = mItemRecoil * item_recoil_offset_coeff"
    item_recoil_rotation_coeff                                      5 [0, 1]                        "Item rotation by recoil = mItemRecoil * item_recoil_rotation_coeff"
    base_item_file                                                  data/entities/base_item.xml [0, 1] "when dropping / throwing the item, this is the base_item that we add the ability component to"
    use_entity_file_as_projectile_info_proxy                        0 [0, 1]                        ""
    shooting_reduces_amount_in_inventory                            0 [0, 1]                        ""
    throw_as_item                                                   0 [0, 1]                        ""
    simulate_throw_as_item                                          0 [0, 1]                        "If 1, the item will be work as normal ability, but throwing animation is played by the user"
    max_amount_in_inventory                                         1 [0, 1]                        ""
    amount_in_inventory                                             1 [0, 1]                        ""
    drop_as_item_on_death                                           1 [0, 1]                        ""
    ui_name                                                         [NOT_SET] [0, 1]                "way to name the weapons"
    use_gun_script                                                  0 [0, 1]                        "If 1, the default ability behaviour is replaced with one that uses the lua gun system."
    is_petris_gun                                                   0 [0, 1]                        "if 1, TODO( PETRI)"
    add_these_child_actions                                         -                               "e.g. 'bullet,bullet,damage' ... actions are parsed into a string. These are added as actual entities when the item is initialized"
    current_slot_durability                                         -1 [0, 1]                       "After this many slots the last slot of the gun is removed. -1 means not initialized/infinite."
    slot_consumption_function                                       _get_gun_slot_durability_default [0, 1] "Name of the lua function in 'gun.lua' that is called to calculate durability of the last slot in the gun"
    mChargeCount                                                    0 [0, 1]                        ""
    mIsInitialized                                                  0 [0, 1]                        ""
 - Objects -----------------------------
    gun_config                                                      -                               "Constants for gun script"
    gunaction_config                                                -                               "Constants for gun script"
 - Privates -----------------------------
    mNextFrameUsable                                                0 [0, 1]                        ""
    mAmmoLeft                                                       0 [0, 1]                        ""
    mReloadFramesLeft                                               0 [0, 1]                        ""
    mNextChargeFrame                                                0 [0, 1]                        ""
    mItemRecoil                                                     0 [0, 1]                        ""

AdvancedFishAIComponent
 - Members -----------------------------
    move_check_range_min                                            16 [0, 2]                       ""
    move_check_range_max                                            64 [0, 2]                       ""
 - Privates -----------------------------
    flock                                                           1 [0, 1]                        ""
    avoid_predators                                                 1 [0, 1]                        ""
    mHasTargetDirection                                             0 [0, 1]                        ""
    mTargetPos                                                      -                               ""
    mTargetVec                                                      -                               ""
    mLastFramesMovementAreaMin                                      -                               ""
    mLastFramesMovementAreaMax                                      -                               ""
    mNumFailedTargetSearches                                        0 [0, 1]                        ""
    mNextFrameCheckAreWeStuck                                       -1 [0, 1]                       ""
    mNextFrameCheckFlockWants                                       -1 [0, 1]                       ""
    mNextFramePredatorAvoidance                                     -1 [0, 1]                       ""
    mScared                                                         0 [0, 1]                        ""
    mWantsToBeInFlock                                               1 [0, 1]                        ""

AltarComponent
 - Members -----------------------------
    recognized_entity_tags                                          -                               ""
    uses_remaining                                                  3 [0, 1]                        ""
 - Privates -----------------------------
    m_recognized_entity_tags                                        -                               ""
    m_recognized_entity_tags_count                                  -                               ""
    m_current_entity_tags                                           -                               ""

AnimalAIComponent
 - Members -----------------------------
    ai_state                                                        0 [0, 20]                       "Current state of ai, defines what the animal is doing"
    ai_state_timer                                                  0 [0, 1000]                     "If not 0, then we wait till this frame to pop current state from our state stack"
    preferred_job                                                   -                               "We always do this job, unless interrupted (i.e. by taking fire damage)"
    escape_if_damaged_probability                                   30 [0, 1]                       "the chance of escaping if someone damages us. only works if 'can_fly = 0 '"
    attack_if_damaged_probability                                   100 [0, 1]                      "the chance of counter-attacking if someone damages us, and we didn't escape"
    eye_offset_x                                                    0 [-100, 100]                   "We cast rays from our position + eye_offset to check if we can see something"
    eye_offset_y                                                    0 [-100, 100]                   "We cast rays from our position + eye_offset to check if we can see something"
    attack_only_if_attacked                                         0 [0, 1]                        "If 1, we never attack anyone unless attacked before by someone"
    dont_counter_attack_own_herd                                    0 [0, 1]                        "If 1, we don't attack members of our herd even if they accidentally attack us"
    creature_detection_range_x                                      50 [0, 2000]                    "When looking for threats/prey this is the max distance from us on the X axis we scan"
    creature_detection_range_y                                      20 [0, 2000]                    "When looking for threats/prey this is the max distance from us on the Y axis we scan"
    creature_detection_angular_range_deg                            90 [0, 90]                      "When looking for threats/prey this is our field of view around the X axis. 90 means we scan the whole 180 degrees around the X axis, to the left and right"
    creature_detection_check_every_x_frames                         120 [0, 5000]                   "Checks for threats/prey take place at least this many frames apart from each other"
    max_distance_to_cam_to_start_hunting                            300 [0, 2000]                   "JobDefault idles before we've been once at least this close to the camera"
    pathfinding_max_depth_no_target                                 50 [0, 5000]                    "The maximum depth (in nodes) path search use when we have not found prey yet"
    pathfinding_max_depth_has_target                                120 [0, 5000]                   "The maximum depth (in nodes) path search use when we have found prey"
    aggressiveness_min                                              80 [0, 100]                     "what's the initial random aggressiveness of this creature"
    aggressiveness_max                                              100 [0, 100]                    "what's the initial random aggressiveness of this creature"
    tries_to_ranged_attack_friends                                  0 [0, 1]                        "if 1, the AI tries to attack whoever it considers a friend based on herd_ids, CHARMED and BERSERK status etc. useful e.g. for healers."
    attack_melee_enabled                                            1 [0, 1]                        "If 1, and melee attack has been configured, we can perform melee attacks"
    attack_dash_enabled                                             0 [0, 1]                        "If 1, and dash attack has been configured, we can perform dash attacks (a long-distance melee attack where we dash towards the enemy)"
    attack_landing_ranged_enabled                                   0 [0, 1]                        "If 1, and ranged attack has been configured, we can perform ranged attacks"
    attack_ranged_enabled                                           0 [0, 1]                        "If 1, and ranged attack has been configured, we can perform ranged attacks"
    attack_knockback_multiplier                                     100 [-100, 100]                 "If not 0, melee and dash attacks cause knockback to target"
    is_static_turret                                                0 [0, 1]                        "If 1, we can only attack in one fixed direction"
    attack_melee_max_distance                                       20 [0, 400]                     "Maximum distance at which we can perform a melee attack"
    attack_melee_action_frame                                       2 [0, 1000]                     "The animation frame during which the melee attack damage is inflicted and visual effects are created"
    attack_melee_frames_between                                     10 [0, 1000]                    "The minimum number of frames we wait between melee attacks"
    attack_melee_damage_min                                         0.4 [0, 100]                    "Melee attack damage inclusive minimum amount. The damage is randomized between melee attack_damage_min and attack_melee_damage_max"
    attack_melee_damage_max                                         0.6 [0, 100]                    "Melee attack damage inclusive maximum amount. The damage is randomized between melee attack_damage_min and attack_melee_damage_max"
    attack_melee_impulse_vector_x                                   0 [-100, 100]                   "The x component of the impulse that is applied to damaged entities"
    attack_melee_impulse_vector_y                                   0 [-100, 100]                   "The y component of the impulse that is applied to damaged entities"
    attack_melee_impulse_multiplier                                 0 [-100, 100]                   "A multiplier applied to attack_melee_impulse"
    attack_melee_offset_x                                           0 [-1000, 1000]                 "Melee attack particle effects are created here"
    attack_melee_offset_y                                           0 [-1000, 1000]                 "Melee attack particle effects are created here"
    attack_melee_finish_enabled                                     0 [0, 1]                        "If 1, we perform a finishing move when our attack would kill the target using the 'attack_finish' animation"
    attack_melee_finish_action_frame                                2 [0, 1000]                     "The animation frame during which the melee attack finishing move damage is inflicted and visual effects are created"
    attack_dash_distance                                            50 [0, 10000]                   "The maximum distance from enemy at which we can perform a dash attack. If a normal melee attack is possible we always do that instead"
    attack_dash_frames_between                                      120 [0, 1200]                   "The minimum number of frames we wait between dash attacks"
    attack_dash_damage                                              0.25 [0, 20]                    "The amount of damage inflicted by the dash attack"
    attack_dash_speed                                               200 [0, 5000]                   "The speed at which we dash"
    attack_dash_lob                                                 0.9 [0, 6]                      "The smaller this value is the more curved our dash attack trajectory is"
    attack_ranged_min_distance                                      10 [0, 10000]                   "The minimum distance from enemy at which we can perform a ranged attack."
    attack_ranged_max_distance                                      160 [0, 10000]                  "The maximum distance from enemy at which we can perform a ranged attack."
    attack_ranged_action_frame                                      2 [0, 1000]                     "The frame of the 'attack_ranged' animation during which the ranged attack actually occurs"
    attack_ranged_frames_between                                    180 [0, 1000]                   "The minimum number of frames we wait between ranged attacks"
    attack_ranged_offset_x                                          0 [-1000, 1000]                 "'attack_ranged_entity_file' is created here when performing a ranged attack"
    attack_ranged_offset_y                                          0 [-1000, 1000]                 "'attack_ranged_entity_file' is created here when performing a ranged attack"
    attack_ranged_use_message                                       0 [0, 1]                        "If 1, we do ranged attacks by sending a Message_UseItem"
    attack_ranged_predict                                           0 [0, 1]                        "If 1, we attempt to predict target movement and shoot accordingly"
    attack_ranged_entity_file                                       data/entities/projectiles/spear.xml [0, 1] "File to projectile entity that is created when performing a ranged attack"
    attack_ranged_entity_count_min                                  1 [0, 1000]                     "Minimum number of projectiles shot when performing a ranged attack"
    attack_ranged_entity_count_max                                  1 [0, 1000]                     "Maximum number of projectiles shot when performing a ranged attack"
    attack_ranged_use_laser_sight                                   0 [0, 1]                        "If 1, we draw a laser sight to our target. Requires entity to have a sprite with tag 'laser_sight'"
    attack_ranged_aim_rotation_enabled                              0 [0, 1]                        ""
    attack_ranged_aim_rotation_speed                                3 [0, 1]                        ""
    attack_ranged_aim_rotation_shooting_ok_angle_deg                10 [0, 1]                       ""
    attack_ranged_state_duration_frames                             45 [0, 1000]                    "How long do we stay in the attack state, before other states are allowed?"
    hide_from_prey                                                  0 [0, 1]                        "If 1, we attempt to hide from our target after a succesful attack"
    hide_from_prey_target_distance                                  200 [0, 10000]                  "The minimum distance from our target where we should move when hiding"
    hide_from_prey_time                                             300 [0, 1]                      "The number of frames we spend hiding and staying hiding"
    food_eating_create_particles                                    1 [0, 1]                        "If 1, we replace eaten cells with particles made of this material"
    eating_area_radius_x                                            3 [-100, 100]                   "1/2 width of the area from which we eat food"
    eating_area_radius_y                                            8 [-100, 100]                   "1/2 height of the area from which we eat food"
    mouth_offset_x                                                  0 [-100, 100]                   "The center of the area from which we eat food"
    mouth_offset_y                                                  0 [-100, 100]                   "The center of the area from which we eat food"
    defecates_and_pees                                              0 [0, 1]                        "If 1, we occasionally take a leak or a dump"
    butt_offset_x                                                   0 [-100, 100]                   "Bodily wastes are created here"
    butt_offset_y                                                   0 [-100, 100]                   "Bodily wastes are created here"
    pee_velocity_x                                                  0 [-1000, 1000]                 "The velocity at which our piss gets shot"
    pee_velocity_y                                                  0 [-1000, 1000]                 "The velocity at which our piss gets shot"
    needs_food                                                      1 [0, 1]                        "If 1, we stop to eat if we encounter 'food_material' cells"
    sense_creatures                                                 1 [0, 1]                        "If 1, we occasionally search our surroundings for prey and threats"
    can_fly                                                         1 [0, 1]                        "If 1, we can fly. Please set 'PathFindingComponent.can_fly' to 1 as well if this is 1"
    can_walk                                                        1 [0, 1]                        "If 1, we can walk. Please set 'PathFindingComponent.can_walk' to 1 as well if this is 1"
    path_distance_to_target_node_to_turn_around                     0 [0, 1000]                     "If we're further than this from target path finding node on the X-axis we turn to face it"
    path_cleanup_explosion_radius                                   6 [0, 1000]                     "If we get stuck on ground we create an explosion this big to clear our surroundings a bit"
    max_distance_to_move_from_home                                  0 [0, 1]                        ""
 - Objects -----------------------------
    attack_melee_finish_config_explosion                            -                               "If we have explosion, it's the setup for it"
 - Privates -----------------------------
    mAiStateStack                                                   -                               "a stack of actions and times they take, we can push new actions to the front and pop them from there"
    mAiStateLastSwitchFrame                                         0 [0, 1]                        "when was the last time we switched a state"
    mAiStatePrev                                                    0 [0, 1]                        "previous AI state"
    mCreatureDetectionNextCheck                                     0 [0, 1]                        "threat/prey check, next time we check for threat/prey"
    mGreatestThreat                                                 0 [0, 1]                        "the entity we consider to be our greatest threat"
    mGreatestPrey                                                   0 [0, 1]                        "the entity we consider to be our most important prey"
    mSelectedMultiAttack                                            -1 [0, 1]                       "which AIAttackComponent attack are we using?"
    mHasFoundPrey                                                   0 [0, 1]                        "1, if we have ever found prey"
    mHasBeenAttackedByPlayer                                        0 [0, 1]                        "1, if we have been ever attacked"
    mHasStartedAttacking                                            0 [0, 1]                        "1, if we have ever started attacking anyone"
    mNearbyFoodCount                                                0 [0, 1]                        "amount of 'food_material' near us"
    mEatNextFrame                                                   0 [0, 1]                        "next frame we can eat"
    mEatTime                                                        0 [0, 1]                        "time we've been constantly eating"
    mFrameNextGiveUp                                                0 [0, 1]                        "next frame we consider ourselves to be stuck"
    mLastFramesMovementAreaMin                                      -                               "AABB min of the area where we've been since the last time we got stuck"
    mLastFramesMovementAreaMax                                      -                               "AABB max of the area where we've been since the last time we got stuck"
    mFoodMaterialId                                                 -1 [0, 1]                       "cached id of 'food_material'"
    mFoodParticleEffectMaterialId                                   -1 [0, 1]                       "cached id of 'food_particle_effect_material'"
    mNextJumpLob                                                    1 [0, 1]                        "we use this for next jump"
    mNextJumpTarget                                                 -                               "we use this for next jump"
    mNextJumpHasVelocity                                            0 [0, 1]                        "we use this for next jump"
    mLastFrameJumped                                                -1 [0, 1]                       "previous frame we launched into a jump"
    mFramesWithoutTarget                                            0 [0, 1]                        ""
    mLastFrameCanDamageOwnHerd                                      -1 [0, 1]                       ""
    mHomePosition                                                   -                               "where our home is located"
    mLastFrameAttackWasDone                                         0 [0, 1]                        "when was the last time we did an attack (not necessarily did damage to anyone though)"
    mNextFrameCanCallFriend                                         0 [0, 1]                        ""
    mNextFrameRespondFriend                                         -1 [0, 1]                       ""
    mHasNoticedPlayer                                               0 [0, 1]                        "if 1, we have noticed player or player projectile"
    mRangedAttackCurrentAimAngle                                    0 [0, 1]                        "which direction does our gun currently point at, physically saying?"
    mRangedAttackNextFrame                                          0 [0, 1]                        "next frame we can perform a ranged attack"
    mMeleeAttackNextFrame                                           0 [0, 1]                        "next frame we can perform a melee attack"
    mNextMeleeAttackDamage                                          0 [0, 1]                        "the amount of damage our next melee attack will cause. used by finishing move logic"
    mMeleeAttacking                                                 0 [0, 1]                        "1, if we're doing a melee attack"
    mMeleeAttackDashNextFrame                                       0 [0, 1]                        "the next frame we can perform a melee attack"
    mCurrentJob                                                     -                               "info about our current job. sorta legacy and could be simplified because the RTS logic is not used anywhere but doesn't have much overhead either."

ArcComponent
 - Members -----------------------------
    lifetime                                                        60 [0, 1]                       "remaining number of frames the arc exists"
 - Privates -----------------------------
    mArcTarget                                                      0 [0, 1]                        "if 'mArcTarget' points to an existing entity a lighting arc will be created between this entity and 'mArcTarget'"

AreaDamageComponent
 - Members -----------------------------
    damage_per_frame                                                10 [0, 256]                     ""
    update_every_n_frame                                            1 [0, 60]                       ""
    death_cause                                                     curse [0, 60]                   ""
    entities_with_tag                                               mortal [0, 1]                   "damage entities with this tag"

AudioComponent
 - Members -----------------------------
    file                                                            -                               ""
    event_root                                                      -                               ""
    audio_physics_material                                          -                               ""
    set_latest_event_position                                       0 [0, 1]                        ""
    play_only_if_visible                                            0 [0, 1]                        "plays sounds only if entity position is on screen and not covered by fog of war"
 - Privates -----------------------------
    m_audio_physics_material                                        0 [0, 1]                        ""
    m_latest_source                                                 -1 [0, 1]                       ""

AudioListenerComponent
 - Members -----------------------------
    z                                                               0 [-500, 500]                   ""

AudioLoopComponent
 - Members -----------------------------
    file                                                            -                               ""
    event_name                                                      -                               ""
    auto_play                                                       0 [0, 1]                        ""
    auto_play_if_enabled                                            0 [0, 1]                        ""
    play_on_component_enable                                        0 [0, 1]                        ""
    calculate_material_lowpass                                      1 [0, 1]                        ""
    set_speed_parameter                                             0 [0, 1]                        ""
    set_speed_parameter_only_based_on_x_movement                    0 [0, 1]                        ""
    set_speed_parameter_only_based_on_y_movement                    0 [0, 1]                        ""
    volume_autofade_speed                                           0 [0, 1]                        ""
 - Privates -----------------------------
    m_volume                                                        0 [0, 1]                        ""
    m_intensity                                                     1 [0, 1]                        ""
    m_source                                                        -1 [0, 1]                       ""

BlackHoleComponent
 - Members -----------------------------
    radius                                                          16 [0, 128]                     ""
    particle_attractor_force                                        2 [0, 32]                       ""
    damage_probability                                              0.25 [0, 1]                     ""
    damage_amount                                                   0.1 [0, 10]                     ""
 - Privates -----------------------------
    m_particle_attractor_id                                         -1 [0, 1]                       ""

BookComponent
 - Members -----------------------------
    TEMP_TEMPY                                                      0 [0, 3.5]                      ""
    TEMP_TEMP_TEMP                                                  0 [0, 3.5]                      ""

BossDragonComponent
 - Members -----------------------------
    speed                                                           1 [0, 10000]                    ""
    speed_hunt                                                      3 [0, 10000]                    ""
    acceleration                                                    3 [0, 10000]                    ""
    direction_adjust_speed                                          1 [0, 10000]                    ""
    direction_adjust_speed_hunt                                     1 [0, 10000]                    ""
    gravity                                                         3 [0, 10000]                    ""
    tail_gravity                                                    30 [0, 10000]                   ""
    part_distance                                                   10 [0, 10000]                   ""
    ground_check_offset                                             0 [0, 10000]                    ""
    eat_ground_radius                                               1 [0, 1e+006]                   ""
    eat_ground                                                      1 [0, 1]                        "does the worm destroy the ground it moves through or not?"
    hitbox_radius                                                   1 [0, 1e+006]                   ""
    bite_damage                                                     2 [0, 10]                       "how much damage does this do when it hits an entity"
    target_kill_radius                                              1 [0, 1e+006]                   ""
    target_kill_ragdoll_force                                       1 [0, 1e+006]                   ""
    hunt_box_radius                                                 512 [0, 10000]                  ""
    random_target_box_radius                                        512 [0, 10000]                  ""
    new_hunt_target_check_every                                     30 [0, 10000]                   ""
    new_random_target_check_every                                   120 [0, 10000]                  ""
    jump_cam_shake                                                  20 [0, 10000]                   ""
    jump_cam_shake_distance                                         256 [0, 10000]                  ""
    eat_anim_wait_mult                                              0.05 [0, 10000]                 ""
    ragdoll_filename                                                -                               ""
 - Privates -----------------------------
    mTargetEntityId                                                 0 [0, 1]                        ""
    mTargetVec                                                      -                               ""
    mGravVelocity                                                   0 [0, 1]                        ""
    mSpeed                                                          0 [0, 1]                        ""
    mRandomTarget                                                   -                               ""
    mLastLivingTargetPos                                            -                               ""
    mNextTargetCheckFrame                                           0 [0, 1]                        ""
    mNextHuntTargetCheckFrame                                       0 [0, 1]                        ""
    mOnGroundPrev                                                   0 [0, 1]                        ""
    mMaterialIdPrev                                                 0 [0, 1]                        ""
    mPhase                                                          0 [0, 1]                        ""
    mNextPhaseSwitchTime                                            0 [0, 1]                        ""
    mPartDistance                                                   2 [0, 1]                        ""
    mIsInitialized                                                  0 [0, 1]                        ""

BuildingUIComponent
 - Members -----------------------------
    pixel_stamp_material                                            wood_player [0, 1]              ""
    entity_filenames                                                -                               ""
    cursor_filename                                                 -                               ""
    can_be_rotated                                                  1 [0, 1]                        ""
 - Privates -----------------------------
    mEntityIndex                                                    0 [0, 1]                        ""
    mEntityFilenames                                                -                               ""
    mPlacedObject                                                   -                               ""
    mCursorObject                                                   -                               ""
    mRotations                                                      0 [0, 1]                        ""

CameraBoundComponent
 - Members -----------------------------
    enabled                                                         1 [0, 1]                        "If enabled, kills this component if it's outside the camera distance"
    distance                                                        250 [0, 1024]                   "Distance in pixels from the center of camera, if outside this distance the entity is destroyed"
    distance_border                                                 20 [0, 1024]                    "Offset towards camera in pixels from 'distance' where the entity is respawned if it was frozen"
    max_count                                                       10 [0, 1024]                    "If more than 'max_count' entities of this type exist the one furthest from camera is destroyed"
    freeze_on_distance_kill                                         1 [0, 1]                        "If true and the entity went too far - this entity will be stored so we can later respawn it where it was destroyed because it got too far from the camera?"
    freeze_on_max_count_kill                                        1 [0, 1]                        "If true and the entity was one too many of its kind - this entity will be stored so we can later respawn it where it was destroyed because it got too far from the camera?"

CardinalMovementComponent
 - Members -----------------------------
    horizontal_movement                                             1 [0, 1]                        "allow horizontal movement"
    vertical_movement                                               1 [0, 1]                        "allow vertical movement"
    intercardinal_movement                                          0 [0, 1]                        "allow intercardinal movement"
 - Privates -----------------------------
    mPrevPos                                                        -                               ""

CellEaterComponent
 - Members -----------------------------
    radius                                                          10 [0, 100]                     ""
    eat_probability                                                 100 [0, 100]                    ""
    only_stain                                                      0 [0, 1]                        ""
    eat_dynamic_physics_bodies                                      1 [0, 1]                        ""
    limited_materials                                               0 [0, 1]                        "if true, will only eat the materials defined in material_list"

CharacterCollisionComponent
 - Members -----------------------------
    getting_crushed_threshold                                       5 [0, 100]                      ""
    moving_up_before_getting_crushed_threshold                      3 [0, 100]                      ""
 - Privates -----------------------------
    getting_crushed_counter                                         0 [0, 1]                        "1.12.2018 - Is this still used?"
    stuck_in_ground_counter                                         0 [0, 1]                        "used this mostly for player to figure out if it's stuck in ground"
    mCollidedHorizontally                                           0 [0, 1]                        ""

CharacterDataComponent
 - Members -----------------------------
    platforming_type                                                0 [0, 3]                        "0 = oldest, 1 = newer, 2 = safest"
    mass                                                            1 [0, 10]                       "1.0 = approx. mass of player"
    buoyancy_check_offset_y                                         -6 [-1000, 1000]                ""
    gravity                                                         100 [0, 250]                    ""
    fly_recharge_spd                                                0 [0, 250]                      ""
    fly_recharge_spd_ground                                         0 [0, 250]                      ""
    flying_needs_recharge                                           0 [0, 1]                        "const variable... player has this as true"
    flying_in_air_wait_frames                                       44 [0, 200]                     "to fix the tap tap tap flying cheese, we wait this many frames before recharging in air"
    flying_recharge_removal_frames                                  8 [0, 20]                       "another fix to the tap tap - this is how many frames from pressing down up we'll remove fly charge"
    climb_over_y                                                    3 [0, 10]                       ""
    check_collision_max_size_x                                      5 [0, 50]                       ""
    check_collision_max_size_y                                      5 [0, 50]                       ""
    is_on_ground                                                    0 [0, 1]                        ""
    is_on_slippery_ground                                           0 [0, 1]                        ""
    ground_stickyness                                               0 [0, 1]                        ""
    effect_hit_ground                                               0 [0, 1]                        ""
    eff_hg_damage_min                                               0 [0, 1]                        "if we want to damage ground when hitting it... this is the place"
    eff_hg_damage_max                                               0 [0, 1]                        "if we want to damage ground when hitting it... this is the place"
    eff_hg_position_x                                               0 [-15, 15]                     ""
    eff_hg_position_y                                               0 [-15, 15]                     ""
    eff_hg_size_x                                                   0 [-15, 15]                     ""
    eff_hg_size_y                                                   0 [-15, 15]                     ""
    eff_hg_velocity_min_x                                           0 [-65, 65]                     ""
    eff_hg_velocity_max_x                                           0 [-65, 65]                     ""
    eff_hg_velocity_min_y                                           0 [-65, 65]                     ""
    eff_hg_velocity_max_y                                           0 [-65, 65]                     ""
    eff_hg_offset_y                                                 0 [-15, 15]                     ""
    eff_hg_update_box2d                                             0 [0, 1]                        "if true, will move physics bodies that it hits"
    eff_hg_b2force_multiplier                                       0.0035 [0, 1]                   "multiplies the velocity with this..."
    destroy_ground                                                  0 [0, 1]                        "how much damage do we do the ground when land on it"
 - Privates -----------------------------
    mFramesOnGround                                                 0 [0, 1]                        ""
    mLastFrameOnGround                                              0 [0, 1]                        ""
    mVelocity                                                       -                               ""
    mFlyingTimeLeft                                                 1000 [0, 1]                     "how much flying energy do we have left?"
    mCollidedHorizontally                                           0 [0, 1]                        "moved this here from CharacterCollisionComponent - since that is multithreaded and we needed a non multithreaded version"

CharacterPlatformingComponent
 - Members -----------------------------
    jump_velocity_x                                                 0 [0, 500]                      ""
    jump_velocity_y                                                 -175 [-500, 0]                  ""
    jump_keydown_buffer                                             2 [0, 10]                       ""
    fly_speed_max_up                                                0 [-2500, 0]                    ""
    fly_speed_max_down                                              0 [-2500, 0]                    ""
    fly_speed_mult                                                  0 [-100, 100]                   "AI stuff"
    fly_speed_change_spd                                            5 [0, 1000]                     "player"
    fly_model_player                                                0 [0, 1]                        "if true, uses player fly model"
    fly_smooth_y                                                    1 [0, 1]                        "if true, smooths out the AI fly model"
    accel_x                                                         1 [0, 1000]                     ""
    accel_x_air                                                     0.1 [0, 1000]                   ""
    pixel_gravity                                                   600 [0, 1000]                   ""
    swim_idle_buoyancy_coeff                                        1.2 [0, 2]                      ""
    swim_down_buoyancy_coeff                                        0.7 [0, 2]                      ""
    swim_up_buoyancy_coeff                                          0.9 [0, 2]                      ""
    swim_drag                                                       0.95 [0, 2]                     "when in water velocity *= swim_drag"
    swim_extra_horizontal_drag                                      0.9 [0, 2]                      "when in water velocity.x *= swim_extra_horizontal_drag"
    mouse_look                                                      1 [0, 1]                        ""
    mouse_look_buffer                                               1 [0, 5]                        ""
    keyboard_look                                                   0 [0, 1]                        "if true, turns based on if left or right has been pressed down"
    turning_buffer                                                  0.1 [0, 2]                      ""
    animation_to_play                                               -                               ""
    animation_to_play_next                                          -                               ""
    run_animation_velocity_switching_threshold                      45 [0, 1000]                    ""
    run_animation_velocity_switching_enabled                        0 [0, 1]                        ""
    turn_animation_frames_between                                   20 [0, 100]                     ""
    precision_jumping_max_duration_frames                           -1 [0, 1]                       "maximum duration of precision jump or knockback. -1 = infinite"
 - Privates -----------------------------
    mExAnimationPos                                                 -                               ""
    mFramesInAirCounter                                             -1 [0, 1]                       ""
    mIsPrecisionJumping                                             0 [0, 1]                        ""
    mPrecisionJumpingTime                                           0 [0, 1]                        ""
    mPrecisionJumpingSpeedX                                         0 [0, 1]                        ""
    mFlyThrottle                                                    0 [0, 1]                        ""
    mSmoothedFlyingTargetY                                          0 [0, 1]                        ""
    mJetpackEmitting                                                -1 [0, 1]                       "-1 = undefined, 0 = not emitting, 1 = emitting"
    mNextTurnAnimationFrame                                         0 [0, 1]                        ""
    mFramesNotSwimming                                              10 [0, 1]                       "0 = currently swimming"
    mFramesSwimming                                                 0 [0, 1]                        "0 = not currently swimming"
    mShouldCrouch                                                   0 [0, 1]                        ""
    mShouldCrouchPrev                                               0 [0, 1]                        ""
    mLastPostureSwitchFrame                                         -1 [0, 1]                       ""
    mLookOverrideLastFrame                                          0 [0, 1]                        ""
    mLookOverrideDirection                                          0 [0, 1]                        ""

CharacterStatsComponent
 - Privates -----------------------------
    stats                                                           -                               ""

CollisionTriggerComponent
 - Members -----------------------------
    width                                                           32 [0, 100]                     ""
    height                                                          32 [0, 100]                     ""
    radius                                                          32 [0, 100]                     ""
    required_tag                                                    mortal [0, 1]                   ""
    remove_component_when_triggered                                 0 [0, 1]                        ""
    destroy_this_entity_when_triggered                              1 [0, 1]                        ""
    timer_for_destruction                                           0 [0, 60]                       ""
    self_trigger                                                    0 [0, 1]                        "if true, the shooter can trigger it"
    skip_self_frames                                                60 [0, 1]                       "skips checks against self during these frames"
 - Privates -----------------------------
    mTimer                                                          0 [0, 1]                        ""

ConsumableTeleportComponent
 - Members -----------------------------
    create_other_end                                                0 [0, 1]                        ""
    is_at_home                                                      0 [0, 1]                        ""
    collision_radius                                                10 [0, 20]                      ""
    target_id                                                       0 [0, 1]                        ""
    id                                                              0 [0, 1]                        ""
    mNextUsableFrame                                                0 [0, 1]                        ""
    mHasOtherEnd                                                    0 [0, 1]                        ""

ControllerGoombaAIComponent
 - Members -----------------------------
    auto_turn_around_enabled                                        1 [0, 1]                        "disable this if you don't want creature to 'look around', while standing still"
    wait_to_turn_around                                             50 [0, 300]                     ""
    wall_hit_wait                                                   10 [0, 300]                     ""
    check_wall_detection                                            1 [0, 1]                        ""
    wall_detection_aabb_min_x                                       0 [-15, 15]                     ""
    wall_detection_aabb_max_x                                       0 [-15, 15]                     ""
    wall_detection_aabb_min_y                                       0 [-15, 15]                     ""
    wall_detection_aabb_max_y                                       0 [-15, 15]                     ""
    check_floor_detection                                           0 [0, 1]                        ""
    floor_detection_aabb_min_x                                      0 [-15, 15]                     ""
    floor_detection_aabb_max_x                                      0 [-15, 15]                     ""
    floor_detection_aabb_min_y                                      0 [-15, 15]                     ""
    floor_detection_aabb_max_y                                      0 [-15, 15]                     ""
 - Privates -----------------------------
    mChangingDirectionCounter                                       -1 [0, 1]                       ""

ControlsComponent
 - Members -----------------------------
    polymorph_hax                                                   0 [0, 1]                        ""
    polymorph_next_attack_frame                                     0 [0, 1]                        ""
    enabled                                                         1 [0, 1]                        ""
    gamepad_indirect_aiming_enabled                                 0 [0, 1]                        ""
    gamepad_fire_on_thumbstick_extend                               0 [0, 1]                        ""
    gamepad_fire_on_thumbstick_extend_threshold                     0.7 [0, 1]                      ""
 - Privates -----------------------------
    mButtonDownFire                                                 0 [0, 1]                        ""
    mButtonFrameFire                                                0 [0, 1]                        ""
    mButtonLastFrameFire                                            -2 [0, 1]                       ""
    mButtonDownFire2                                                0 [0, 1]                        ""
    mButtonFrameFire2                                               0 [0, 1]                        ""
    mButtonDownAction                                               0 [0, 1]                        ""
    mButtonFrameAction                                              0 [0, 1]                        ""
    mButtonDownThrow                                                0 [0, 1]                        ""
    mButtonFrameThrow                                               0 [0, 1]                        ""
    mButtonDownInteract                                             0 [0, 1]                        ""
    mButtonFrameInteract                                            0 [0, 1]                        ""
    mButtonDownLeft                                                 0 [0, 1]                        ""
    mButtonFrameLeft                                                0 [0, 1]                        ""
    mButtonDownRight                                                0 [0, 1]                        ""
    mButtonFrameRight                                               0 [0, 1]                        ""
    mButtonDownUp                                                   0 [0, 1]                        ""
    mButtonFrameUp                                                  0 [0, 1]                        ""
    mButtonDownDown                                                 0 [0, 1]                        ""
    mButtonFrameDown                                                0 [0, 1]                        ""
    mButtonDownJump                                                 0 [0, 1]                        ""
    mButtonFrameJump                                                0 [0, 1]                        ""
    mButtonDownRun                                                  0 [0, 1]                        ""
    mButtonFrameRun                                                 0 [0, 1]                        ""
    mButtonDownFly                                                  0 [0, 1]                        ""
    mButtonFrameFly                                                 0 [0, 1]                        ""
    mButtonDownDig                                                  0 [0, 1]                        ""
    mButtonFrameDig                                                 0 [0, 1]                        ""
    mButtonDownChangeItemR                                          0 [0, 1]                        ""
    mButtonFrameChangeItemR                                         0 [0, 1]                        ""
    mButtonCountChangeItemR                                         0 [0, 1]                        "note these have special count property"
    mButtonDownChangeItemL                                          0 [0, 1]                        ""
    mButtonFrameChangeItemL                                         0 [0, 1]                        ""
    mButtonCountChangeItemL                                         0 [0, 1]                        "note these have special count property"
    mButtonDownInventory                                            0 [0, 1]                        ""
    mButtonFrameInventory                                           0 [0, 1]                        ""
    mButtonDownHolsterItem                                          0 [0, 1]                        ""
    mButtonFrameHolsterItem                                         0 [0, 1]                        ""
    mButtonDownDropItem                                             0 [0, 1]                        ""
    mButtonFrameDropItem                                            0 [0, 1]                        ""
    mButtonDownKick                                                 0 [0, 1]                        ""
    mButtonFrameKick                                                0 [0, 1]                        ""
    mButtonDownEat                                                  0 [0, 1]                        ""
    mButtonFrameEat                                                 0 [0, 1]                        ""
    mButtonDownTransformLeft                                        0 [0, 1]                        ""
    mButtonFrameTransformLeft                                       0 [0, 1]                        ""
    mButtonDownTransformRight                                       0 [0, 1]                        ""
    mButtonFrameTransformRight                                      0 [0, 1]                        ""
    mButtonDownTransformUp                                          0 [0, 1]                        ""
    mButtonFrameTransformUp                                         0 [0, 1]                        ""
    mButtonCountTransformUp                                         0 [0, 1]                        ""
    mButtonDownTransformDown                                        0 [0, 1]                        ""
    mButtonFrameTransformDown                                       0 [0, 1]                        ""
    mButtonCountTransformDown                                       0 [0, 1]                        ""
    mFlyingTargetY                                                  0 [0, 1]                        ""
    mAimingVector                                                   -                               ""
    mAimingVectorNormalized                                         -                               "Aiming vector normalized to unit sphere."
    mAimingVectorNonZeroLatest                                      -                               ""
    mGamepadAimingVectorRaw                                         -                               ""
    mJumpVelocity                                                   -                               "used mostly by AI only?"
    mMousePosition                                                  -                               ""
    mMousePositionRaw                                               -                               ""
    mMousePositionRawPrev                                           -                               ""
    mMouseDelta                                                     -                               ""
    mGamepadIndirectAiming                                          -                               ""

CrawlerAnimalComponent
 - Members -----------------------------
    ray_length                                                      5 [0, 100]                      ""
    ray_count                                                       16 [0, 64]                      ""
    gravity                                                         600 [0, 10000]                  ""
    terminal_velocity                                               600 [0, 10000]                  ""
    speed                                                           0.2 [0, 10000]                  ""
    give_up_area_radius                                             20 [0, 1000]                    ""
    give_up_time                                                    45 [0, 1000]                    ""
    attack_from_ceiling_check_ray_length                            128 [0, 1000]                   ""
    attack_from_ceiling_check_every_n_frames                        15 [0, 1000]                    ""
    collision_damage                                                0.25 [0, 1000]                  ""
    collision_damage_radius                                         10 [0, 1000]                    ""
    collision_damage_frames_between                                 10 [0, 1000]                    ""
    animate                                                         1 [0, 1]                        ""
 - Privates -----------------------------
    mDir                                                            1 [0, 1]                        ""
    mFrameNextGiveUp                                                0 [0, 1]                        ""
    mFrameNextDamage                                                0 [0, 1]                        ""
    mFrameNextAttackFromCeilingCheck                                0 [0, 1]                        ""
    mMin                                                            -                               ""
    mMax                                                            -                               ""
    mPrevNonSnappedPosition                                         -                               ""
    mPrevCellPosition                                               -                               ""
    mPrevCellPosition2                                              -                               ""
    mPrevCellPosition3                                              -                               ""
    mPrevCellPosition4                                              -                               ""
    mPrevCellPosition5                                              -                               ""
    mPrevCellPosition6                                              -                               ""
    mPrevCellPosition7                                              -                               ""
    mPrevCellPosition8                                              -                               ""
    mLatestPosition                                                 -                               ""
    mPrevFalling                                                    0 [0, 1]                        ""
    mIsInitialized                                                  0 [0, 1]                        ""
    mVelocityY                                                      0 [0, 1]                        ""
    mAngle                                                          0 [0, 1]                        ""
    mMovementStepAccumulator                                        0 [0, 1]                        ""

DamageModelComponent
 - Members -----------------------------
    hp                                                              1 [0, 4]                        "hit points at the moment"
    max_hp                                                          0 [0, 4]                        "the maximum hp that this can have, we'll set this when loading"
    max_hp_cap                                                      0 [0, 12]                       "Note(Petri): Is this used anywhere? - the maximum 'max_hp' that this can have, <= 0 means no limits"
    critical_damage_resistance                                      0 [0, 1]                        "0.0 = all critical damage multiplier is applied. 1.0 = no critical damage multiplier is applied"
    invincibility_frames                                            0 [0, 1024]                     "if positive, doesn't take damage"
    falling_damages                                                 1 [0, 1]                        "do we take fall damage"
    falling_damage_height_min                                       70 [0, 1]                       "how far do we need to fall to take damage, we start with this height, the peasant takes min damage from this"
    falling_damage_height_max                                       250 [0, 1]                      "after this the peasant always takes the maximum fall damage"
    falling_damage_damage_min                                       0.1 [0, 1]                      "when we fall over height_min we take this much, lineary ramping to damage_max"
    falling_damage_damage_max                                       1.2 [0, 1]                      "when we fall over height_min we take this much, lineary ramping to damage_max"
    air_needed                                                      1 [0, 1]                        "Do we breath, can we take damage from not breathing?"
    air_in_lungs                                                    5 [0, 1]                        "How much air do we have in our lungs? - after the air runs out we take damage"
    air_in_lungs_max                                                5 [0, 1]                        "how much air can we have in our lungs, it's filled to this point if we're not in water"
    air_lack_of_damage                                              0.2 [0, 1]                      "(* dt)... damage in a second if we're in the water"
    minimum_knockback_force                                         0 [0, 1]                        "Minimum knockback force required to do the knockback"
    materials_damage                                                1 [0, 1]                        "should materials do damage or not?"
    material_damage_min_cell_count                                  4 [0, 1]                        "if material damage is received from less than 'material_damage_min_cell_count' this frame, it is ignored"
    materials_that_damage                                           acid [0, 1]                     "list of materials that do damage, separated by ',' e.g. 'acid, fire, smoke'"
    materials_how_much_damage                                       0.1 [0, 1]                      "list of damage amount per material in materials_that_damage, separated by ','"
    physics_objects_damage                                          0 [0, 1]                        "if true, will take damage from physics objects that hit it"
    materials_create_messages                                       0 [0, 1]                        "should collisions with certain materials create messages or not?"
    materials_that_create_messages                                  meat [0, 1]                     "list of materials that generate CollisionWithCell messages, separated by ',' e.g. 'acid, fire, smoke'"
    ragdoll_filenames_file                                          data/temp/ragdoll/filenames.txt [0, 1] "the file from which to load a ragdoll on death'"
    ragdoll_material                                                meat [0, 1]                     "what material is the ragdoll made out of"
    ragdoll_offset_x                                                0 [0, 1]                        "where should the ragdoll be created relative to our entity position'"
    ragdoll_offset_y                                                0 [0, 1]                        "where should the ragdoll be created relative to our entity position'"
    blood_material                                                  blood_fading [0, 1]             "this is the material that gets thrown as particles when this entity takes damage"
    blood_spray_material                                            -                               "this is the material that gets thrown as particles when this entity sprays blood on death"
    blood_spray_create_some_cosmetic                                0 [0, 1]                        "if true, we force some blood spray particles to be cosmetic (can be enabled to avoid making a huge mess of blood spray)"
    blood_multiplier                                                1 [0, 10]                       "how much blood, this is the multiplier used for sprouting lots or little blood"
    ragdoll_blood_amount_absolute                                   -1 [-1, 1000]                   "if > -1, this is the absolute amount of blood we share between particle emitters in the ragdoll"
    blood_sprite_directional                                        -                               "this sprite is loaded at damage position if we take damage that creates a blood effect"
    blood_sprite_large                                              -                               "this sprite is loaded at damage position if we take explosion/heavy damage"
    create_ragdoll                                                  1 [0, 1]                        "if 0, we skip ragdoll creation on death"
    ragdollify_child_entity_sprites                                 0 [0, 1]                        "if 1, we ragdollify child entity sprites"
    wait_for_kill_flag_on_death                                     0 [0, 1]                        "if 1, we wont kill the entity along with kill fx and ragdoll until 'kill' is 1"
    kill_now                                                        0 [0, 1]                        "if 1, we wont kill the entity along with kill fx and ragdoll until 'kill_now' is 1"
    drop_items_on_death                                             1 [0, 1]                        "drop the abilities as items on death?"
    in_liquid_shooting_electrify_prob                               0 [0, 100]                      "when shooting underwater how likely are we to electrify the water"
    wet_status_effect_damage                                        0 [0, 0.1]                      "how much damage per 10 frames is done if entity has 'wet' status effect"
    is_on_fire                                                      0 [0, 1]                        "Tells us we're on fire or not"
    fire_probability_of_ignition                                    0.5 [0, 1]                      "what is the probability that we'll ignite, 0 means won't ever ignite"
    fire_how_much_fire_generates                                    4 [0, 10]                       "how many fire particles do we generate each frame"
    fire_damage_ignited_amount                                      0.0003 [0, 2]                   "how much damage does being ignited do?"
    fire_damage_amount                                              0.2 [0, 2]                      "how much damage does fire do?, 0.2 is pretty good"
    mLastElectricityResistanceFrame                                 -2147483648 [0, 1]              "Last frame electricity has no effect. Should not be private!"
 - Objects -----------------------------
    damage_multipliers                                              -                               "the multipliers applied to different types of damage"
 - Privates -----------------------------
    mIsOnFire                                                       0 [0, 1]                        "private variable to check when we're on fire and not"
    mFireProbability                                                100 [0, 1]                      "this gets decreased if we can't ignite anything else"
    mFireFramesLeft                                                 0 [0, 1]                        "this is the remaining frames we're on fire"
    mFireDurationFrames                                             0 [0, 1]                        "this is the total duration in frames we're on fire"
    mFireTriedIgniting                                              0 [0, 1]                        "private variable to check when we could have been ignited or not"
    mLastCheckX                                                     0 [0, 1]                        "an optimization, so we don't have to check everything every frame"
    mLastCheckY                                                     0 [0, 1]                        "an optimization, so we don't have to check everything every frame"
    mLastCheckTime                                                  0 [0, 1]                        "an optimization, so we don't have to check everything every frame"
    mLastMaterialDamageFrame                                        0 [0, 1]                        "this is the last frame we took material damage"
    mFallIsOnGround                                                 0 [0, 1]                        "for fall damage, keeps a private variable about if we're on ground or not"
    mFallHighestY                                                   3.40282e+038 [0, 1]             "private var to keep track of how high have we flown to"
    mFallCount                                                      0 [0, 1]                        "how many times have we fallen? This is used to make sure we don't take damage from the first fall"
    mAirAreWeInWater                                                0 [0, 1]                        "a private variable to track our state in drowning"
    mAirFramesNotInWater                                            0 [0, 1]                        "how many frames have been with air to breathe"
    mAirDoWeHave                                                    0 [0, 1]                        "a private variable to track our state in drowning"
    mTotalCells                                                     0 [0, 1]                        "how many cells are there total"
    mLiquidCount                                                    0 [0, 1]                        "how many of the cells are liquid"
    mDamageMaterials                                                -                               "NOTE! Sorted! a list of materials that do damage (materials_that_damage)"
    mDamageMaterialsHowMuch                                         -                               "NOTE! Sorted! a list of materials that do damage (materials_that_damage)"
    mCollisionMessageMaterials                                      -                               "NOTE! Sorted! a list of materials that create messages (materials_that_create_messages)"
    mCollisionMessageMaterialCountsThisFrame                        -                               "Number of cells per collided with this frame. Order matches mCollisionMessageMaterials"
    mMaterialDamageThisFrame                                        -                               "A list of damage per material that damages us. In same order as materials"
    mFallDamageThisFrame                                            0 [0, 1]                        "Amount of fall damage received this frame"
    mElectricityDamageThisFrame                                     0 [0, 1]                        "Amount of electricity damage received this frame"
    mPhysicsDamageThisFrame                                         0 [0, 1]                        "max physics damage we have taken this round"
    mPhysicsDamageVecThisFrame                                      -                               "direction of physics damage"
    mPhysicsDamageLastFrame                                         0 [0, 1]                        "frame number when we took physics damage"
    mLastDamageFrame                                                -120 [0, 1]                     "frame number when we took any damage"
    mHpBeforeLastDamage                                             0 [0, 1]                        "how much hp did we have a while ago?"

DamageNearbyEntitiesComponent
 - Members -----------------------------
    radius                                                          10 [0, 1]                       ""
    damage_min                                                      0.1 [0, 1]                      ""
    damage_max                                                      0.2 [0, 1]                      ""
    target_vec_max_len                                              5 [0, 1]                        ""
    knockback_multiplier                                            1 [0, 1]                        ""
    time_between_damaging                                           20 [0, 1]                       ""
    damage_description                                              bite [0, 1]                     ""
    target_tag                                                      mortal [0, 1]                   ""
 - Privates -----------------------------
    mVelocity                                                       -                               ""
    mNextDamageFrame                                                0 [0, 1]                        ""

DebugFollowMouseComponent

DebugLogMessagesComponent
 - Members -----------------------------
    TEMP_TEMPY                                                      0 [0, 3.5]                      ""
    TEMP_TEMP_TEMP                                                  0 [0, 3.5]                      ""

DebugSpatialVisualizerComponent
 - Members -----------------------------
    min_x                                                           0 [0, 1]                        ""
    min_y                                                           0 [0, 1]                        ""
    max_x                                                           0 [0, 1]                        ""
    max_y                                                           0 [0, 1]                        ""
    color                                                           4294967295 [0, 1]               ""

DieIfSpeedBelowComponent
 - Members -----------------------------
    min_speed                                                       1 [0, 1000]                     "The entity that owns this component is killed if its speed (via VelocityComponent) falls below this value."
    mMinSpeedSquared                                                0 [0, 1]                        ""

DroneLauncherComponent
 - Members -----------------------------
    drone_entity_file                                               data/entities/misc/player_drone.xml [0, 1] ""

DrugEffectComponent
 - Members -----------------------------
    change_speed                                                    1 [0, 100]                      ""
    alcohol_amount                                                  0 [0, 3]                        ""
    hallucinogen_amount                                             0 [0, 3]                        ""
    nightvision_amount                                              0 [0, 3]                        ""
    stoned_amount                                                   0 [0, 3]                        ""
    alcohol_wear_off_speed                                          0.02 [0, 100]                   ""
    hallucinogen_wear_off_speed                                     0.005 [0, 100]                  ""
    nightvision_wear_off_speed                                      0.002 [0, 100]                  ""
    stoned_wear_off_speed                                           0.005 [0, 100]                  ""
 - Objects -----------------------------
    drug_fx_target                                                  -                               ""
 - Privates -----------------------------
    mAlcoholAmount                                                  0 [0, 1]                        ""
    mHallucinogenAmount                                             0 [0, 1]                        ""
    mNightvisionAmount                                              0 [0, 1]                        ""
    mStonedAmount                                                   0 [0, 1]                        ""
    mDrugFxCurrent                                                  -                               ""

ElectricChargeComponent
 - Members -----------------------------
    charge_time_frames                                              120 [0, 240]                    ""
    fx_velocity_max                                                 120 [0, 240]                    ""
    electricity_emission_interval_frames                            5 [0, 10]                       ""
    fx_emission_interval_min                                        2 [0, 20]                       ""
    fx_emission_interval_max                                        15 [0, 30]                      ""
    charge                                                          0 [0, 1]                        ""

ElectricityComponent
 - Members -----------------------------
    energy                                                          1000 [0, 10000]                 ""
    probability_to_heat                                             0 [0, 1]                        ""
    speed                                                           32 [0, 10000]                   ""
    splittings_min                                                  0 [0, 10000]                    ""
    splittings_max                                                  0 [0, 10000]                    ""
    splitting_energy_min                                            0 [0, 10000]                    ""
    splitting_energy_max                                            0 [0, 10000]                    ""
    hack_is_material_crack                                          0 [0, 1]                        ""
    hack_is_set_fire                                                0 [0, 1]                        "if set will set the thing on fire where this is located at"
 - Privates -----------------------------
    mSplittingsLeft                                                 0 [0, 1]                        ""
    mSplittingEnergy                                                0 [0, 1]                        ""
    mAvgDir                                                         -                               ""
    mPrevPos                                                        -                               ""
    mPrevMaterial                                                   0 [0, 1]                        ""
    mShouldPlaySound                                                1 [0, 1]                        ""

ElectricityReceiverComponent
 - Members -----------------------------
    offset_x                                                        0 [1, 3]                        ""
    offset_y                                                        0 [1, 3]                        ""
    radius                                                          1 [1, 3]                        ""
    active_time_frames                                              1 [1, 15]                       ""
    switch_on_msg_interval_frames                                   0 [0, 60]                       ""
 - Privates -----------------------------
    mLastFrameElectrified                                           -1000 [0, 1]                    ""
    mNextSwitchOnMsgFrame                                           0 [0, 1]                        ""

ElectricitySourceComponent
 - Members -----------------------------
    radius                                                          5 [1, 16]                       ""
    emission_interval_frames                                        15 [1, 10]                      ""
 - Privates -----------------------------
    mNextFrameEmitElectricity                                       0 [0, 1]                        ""

EndingMcGuffinComponent
 - Members -----------------------------
    TEMP_TEMPY                                                      0 [0, 3.5]                      ""
    TEMP_TEMP_TEMP                                                  0 [0, 3.5]                      ""

EnergyShieldComponent
 - Members -----------------------------
    radius                                                          16 [0, 100]                     ""
    damage_multiplier                                               1.5 [0, 10]                     ""
    max_energy                                                      1 [0, 10]                       ""
    energy_required_to_shield                                       0.2 [0, 10]                     ""
    recharge_speed                                                  1 [0, 10]                       ""
    sector_degrees                                                  360 [0, 360]                    "if less than 180 we only provide partial cover to the current direction of the entity"
    energy                                                          0 [0, 3]                        ""
 - Privates -----------------------------
    mPrevPosition                                                   -                               ""

ExplodeOnDamageComponent
 - Members -----------------------------
    explode_on_death_percent                                        1 [0, 1]                        "rolls a dice (0 - 1) if we explode on death"
    explode_on_damage_percent                                       1 [0, 1]                        "rolls a dice (0 - 1) if we explode on damage"
    physics_body_modified_death_probability                         0 [0, 1]                        "if we get message about the physics body being modified, do we explode on what percent"
    physics_body_destruction_required                               0.5 [0, 1]                      "how big of percent of our body, do we need to lose before we explode"
 - Objects -----------------------------
    config_explosion                                                -                               "if we have explosion, it's the setup for it"
 - Privates -----------------------------
    mDone                                                           0 [0, 1]                        ""

ExplosionComponent
 - Members -----------------------------
    timeout_frames                                                  0 [0, 180]                      "for timer"
    timeout_frames_random                                           0 [0, 180]                      "a random value between 0 and 'timout_frames_random' is added to timer"
    kill_entity                                                     1 [0, 1]                        "if 1, we kill the entity when exploding"
    mTimerTriggerFrame                                              -1 [0, 1]                       ""
 - Objects -----------------------------
    config_explosion                                                -                               "setup for out explosion"

FishAIComponent
 - Members -----------------------------
    direction                                                       0 [-1, 1]                       ""
    speed                                                           100 [1, 1000]                   ""
 - Privates -----------------------------
    velocity                                                        -                               ""
    stuck_counter                                                   0 [0, 1]                        ""
    mLastCheckPos                                                   -                               ""

FlyingComponent
 - Members -----------------------------
    type                                                            0 [0, 1]                        "type of flight, 1 = perlin noise"
    perlin_freq                                                     0.2 [0, 1]                      "frequency of the perlin noise sampling"
    perlin_time_freq                                                0.3 [0, 1]                      "t *= perlin_time_freq"
    perlin_wind_x                                                   0 [-1, 1]                       "wind velocity that gets added to the samples"
    perlin_wind_y                                                   0 [-1, 1]                       "wind velocity that gets added to the samples"

FogOfWarRadiusComponent
 - Members -----------------------------
    radius                                                          256 [0, 1024]                   "256 is the default player has"

FogOfWarRemoverComponent
 - Members -----------------------------
    radius                                                          140 [0, 2000]                   ""

FossilComponent
 - Members -----------------------------
    count_min                                                       0 [0, 1]                        ""
    count_max                                                       0 [0, 1]                        ""
    seed                                                            1 [0, 1]                        ""
    material                                                        bone [0, 1]                     "material that the fossil is made out of, or is_visual=1 then it's material that the seed is made out of"
    image_file                                                      -                               ""
 - Privates -----------------------------
    material_id                                                     -1 [0, 1]                       ""
    mImageData                                                      -                               ""

GameAreaEffectComponent
 - Members -----------------------------
    radius                                                          0 [0, 3.5]                      "what's the radius (in pixels) of the area effect"
    collide_with_tag                                                hittable [0, 1]                 "the tags we're looking for"
    frame_length                                                    -1 [0, 1]                       "if not 0 will reapply this effect after this many frames have gone by"
 - Privates -----------------------------
    mEntitiesAppliedOutTo                                           -                               ""
    mEntitiesAppliedFrame                                           -                               ""

GameEffectComponent
 - Members -----------------------------
    custom_effect_id                                                -                               "if 'effect' is set to 'CUSTOM', this will define effect uniqueness."
    frames                                                          -1 [0, 1]                       "how many frames does it affect -1 = forever"
    exclusivity_group                                               0 [0, 1]                        "if > 0, previous game effects with the same exclusivity group as new one will be removed when calling LoadGameEffectEntityTo"
    report_block_msg                                                1 [0, 1]                        "to disable the block message that rises"
    disable_movement                                                0 [0, 1]                        "if set, will disable movement"
    ragdoll_effect_custom_entity_file                               -                               "an entity that is loaded to each ragdoll part if 'ragdoll_effect' is set to 'CUSTOM_RAGDOLL_ENTITY'"
    ragdoll_fx_custom_entity_apply_only_to_largest_body             0 [0, 1]                        "if 1, 'ragdoll_effect_custom_entity_file' is loaded only to the largest piece in the ragdoll "
    polymorph_target                                                -                               "when doing a polymorph, this is what we convert it to"
    mSerializedData                                                 -                               "polymorph stores the serialized entity here..."
    mCaster                                                         0 [0, 1]                        "Contains a handle to the caster of this GameEffect"
    mCasterHerdId                                                   0 [0, 1]                        "Contains the herd if of the caster of this GameEffect"
    teleportation_probability                                       600 [0, 1]                      "How likely is it that we teleport, larger = less often"
    teleportation_delay_min_frames                                  30 [0, 1]                       "Never teleports more often that this"
    teleportation_radius_min                                        128 [0, 1]                      ""
    teleportation_radius_max                                        1024 [0, 1]                     ""
    teleportations_num                                              0 [0, 1]                        "How many times has this GameEffectComponent teleported the owner?"
    caused_by_stains                                                0 [0, 1]                        "Did we occur because someone got stained?"
    mInvisible                                                      0 [0, 1]                        "Are we invisible?"
    mCounter                                                        0 [0, 1]                        "Counts stuff"
    mCooldown                                                       0 [0, 1]                        "Counts cooldown"

GameLogComponent
 - Members -----------------------------
    report_death                                                    1 [0, 1]                        "switches on reporting things"
    report_damage                                                   0 [0, 1]                        "if set, will report when receiving damage"
    report_new_biomes                                               1 [0, 1]                        "if false, won't report when player enters new biomes"
 - Privates -----------------------------
    mNewBiomeCheckFrame                                             0 [0, 1]                        ""

GameStatsComponent
 - Members -----------------------------
    name                                                            -                               "no one uses the name variable on entity, so we have to do this to make it happen"
    stats_filename                                                  -                               "also generated from the gunk"
    is_player                                                       0 [0, 1]                        "if true, will use the session file for loading stats"
    extra_death_msg                                                 -                               "set when e.g. polymorphed"

GasBubbleComponent
 - Members -----------------------------
    acceleration                                                    -1 [-100, 0]                    ""
    max_speed                                                       20 [0, 20]                      ""
 - Privates -----------------------------
    mVelocity                                                       0 [0, 1]                        ""

GenomeDataComponent
 - Members -----------------------------
    is_predator                                                     0 [0, 1]                        "Predators are considered threats by other species and hunt for food."
    food_chain_rank                                                 0 [0, 200]                      "0 means king of the hill. Greater number = more likely to get eaten by other species."

GhostComponent
 - Members -----------------------------
    speed                                                           5 [0, 1]                        "pixels per second"
    new_hunt_target_check_every                                     0 [0, 1]                        "how often do we look for targets"
    hunt_box_radius                                                 512 [0, 1]                      ""
    aggressiveness                                                  100 [0, 1]                      "if higher than relations then will attack"
    max_distance_from_home                                          300 [0, 1]                      "how far from home can we go?"
    die_if_no_home                                                  1 [0, 1]                        "if set to false will die, if it can't find home"
    target_tag                                                      player_unit [0, 1]              "if something else (like mortal), will attack the home"
 - Privates -----------------------------
    mEntityHome                                                     0 [0, 1]                        "where is our home?"
    mFramesWithoutHome                                              0 [0, 1]                        ""
    mTargetPosition                                                 -                               ""
    mTargetEntityId                                                 0 [0, 1]                        ""
    mRandomTarget                                                   -                               ""
    mNextTargetCheckFrame                                           0 [0, 1]                        ""

GodInfoComponent
 - Members -----------------------------
    mana_current                                                    0 [0, 1000]                     "How much mana the player now has to use"
    mana_max                                                        500 [0, 1000]                   "Max size of the mana pool"
    gold                                                            0 [0, 1000]                     "How much gold the player has"
 - Privates -----------------------------
    god_entity                                                      -                               ""

GunComponent
 - Privates -----------------------------
    mLuaManager                                                     -                               ""

HealthBarComponent

HitEffectComponent
 - Members -----------------------------
    value                                                           0 [0, 100]                      "Usage depends on selected 'effect_hit'"
    value_string                                                    -                               "Usage depends on selected 'effect_hit'"

HitboxComponent
 - Members -----------------------------
    is_player                                                       0 [0, 1]                        ""
    is_enemy                                                        1 [0, 1]                        ""
    is_item                                                         0 [0, 1]                        ""
    aabb_min_x                                                      -5 [-15, 15]                    ""
    aabb_max_x                                                      5 [-15, 15]                     ""
    aabb_min_y                                                      -5 [-15, 15]                    ""
    aabb_max_y                                                      5 [-15, 15]                     ""
    damage_multiplier                                               1 [0, 1]                        "All damage from hits to this hitbox is multiplied with this value before applying it."
 - Privates -----------------------------
    dead                                                            0 [0, 1]                        ""

HomingComponent
 - Members -----------------------------
    target_tag                                                      homing_target [0, 1]            ""
    target_who_shot                                                 0 [0, 1]                        "If 1, targets who shot the projectile, ignores 'target_tag'."
    detect_distance                                                 150 [0, 1000]                   ""
    homing_velocity_multiplier                                      0.9 [-100, 100]                 ""
    homing_targeting_coeff                                          160 [0, 1000]                   ""
 - Privates -----------------------------
    mPredefinedTarget                                               0 [0, 1]                        "If set, we track this entity"

HotspotComponent
 - Members -----------------------------
    transform_with_scale                                            1 [0, 1]                        ""
    sprite_hotspot_name                                             -                               ""

IKLimbAttackerComponent
 - Members -----------------------------
    radius                                                          54 [0, 1]                       ""
    leg_velocity_coeff                                              15 [0, 1]                       ""
 - Privates -----------------------------
    mTargetEntity                                                   0 [0, 1]                        ""
    mState                                                          0 [0, 1]                        ""
    mStateTimer                                                     0 [0, 1]                        ""

IKLimbComponent
 - Members -----------------------------
    length                                                          40 [0, 1]                       ""
    thigh_extra_lenght                                              2 [0, 1]                        ""
    mJointSideInterpolation                                         0 [0, 1]                        ""

IKLimbWalkerComponent
 - Members -----------------------------
    ground_attachment_min_spread                                    16 [0, 1]                       ""
    ground_attachment_max_tries                                     10 [0, 1]                       ""
    ground_attachment_max_angle                                     0.8 [0, 1]                      ""
    ground_attachment_ray_length_coeff                              1.15 [0, 1]                     ""
    leg_velocity_coeff                                              15 [0, 1]                       ""
    affect_flying                                                   0 [0, 1]                        "if set, will cause the mFlyingTime (in CharacterDataComponent) of the parent to be 0 or 1 depending on if we're touching anything"
    mState                                                          0 [0, 1]                        "0 = detached, 1 = attached"

IngestionComponent
 - Members -----------------------------
    DEBUG_allmaterials                                              0 [0, 1]                        "if set to true will track all materials all the time..."

InheritTransformComponent
 - Members -----------------------------
    use_root_parent                                                 0 [0, 1]                        "if 1, we use the root of our entity hierarchy instead of the immediate parent"
    only_position                                                   0 [0, 1]                        "if 1, we only inherit position. it is calculated as follows: parent_position + parent_offset * parent_scale"
    parent_hotspot_tag                                              -                               "if set, we apply the offset of parent HotSpot with this tag"
    parent_sprite_id                                                -1 [0, 1]                       "if >= 0, the Nth sprite transform in parent entity is inherited"
    always_use_immediate_parent_rotation                            0 [0, 1]                        "if 1, we use the immediate parent for rotation, no matter what other properties say"
    rotate_based_on_x_scale                                         0 [0, 1]                        "if 1, the rotation is set to 0 deg if scale >= 0 else to 180 deg"
 - Privates -----------------------------
    mUpdateFrame                                                    -1 [0, 1]                       ""

Inventory2Component
 - Members -----------------------------
    quick_inventory_slots                                           10 [0, 30]                      ""
    full_inventory_slots_x                                          8 [0, 30]                       ""
    full_inventory_slots_y                                          8 [0, 30]                       ""
 - Privates -----------------------------
    mActiveItem                                                     0 [0, 1]                        "NOTE: Don't attempt to directly change the value of this field via lua code. It will probably break the game logic in obvious or subtle ways."
    mActualActiveItem                                               0 [0, 1]                        "NOTE: Don't attempt to directly change the value of this field via lua code. It will probably break the game logic in obvious or subtle ways."
    mActiveStash                                                    0 [0, 1]                        ""
    mItemHolstered                                                  0 [0, 1]                        ""
    mInitialized                                                    0 [0, 1]                        ""
    mForceRefresh                                                   0 [0, 1]                        ""
    mSmoothedItemXOffset                                            0 [0, 1]                        ""
    mLastItemSwitchFrame                                            0 [0, 1]                        ""
    mIntroEquipItemLerp                                             1 [0, 1]                        ""

InventoryComponent
 - Members -----------------------------
    ui_container_type                                               1 [0, 1]                        "UI_CONTAINER_TYPES enum"
    ui_element_sprite                                               data/ui_gfx/inventory/inventory_box.png [0, 1] "ui back sprite"
    actions                                                         -                               "list of actions, used for serialization"
 - Privates -----------------------------
    update_listener                                                 -                               "listener to keep ui up with ability changes"
    items                                                           -                               ""

InventoryGuiComponent
 - Members -----------------------------
    has_opened_inventory_edit                                       0 [0, 1]                        ""
    wallet_money_target                                             0 [0, 1]                        ""
 - Privates -----------------------------
    imgui                                                           -                               ""
    mLastFrameInteracted                                            -100 [0, 1]                     ""
    mLastFrameActionsVisible                                        -1 [0, 1]                       ""
    mLastPurchasedAction                                            -                               ""
    mActive                                                         0 [0, 1]                        ""
    mAlpha                                                          1 [0, 1]                        ""
    mBackgroundOverlayAlpha                                         0 [0, 1]                        ""

ItemAIKnowledgeComponent
 - Members -----------------------------
    is_ranged_weapon                                                0 [0, 1]                        ""
    is_throwable_weapon                                             0 [0, 1]                        ""
    is_melee_weapon                                                 0 [0, 1]                        ""
    is_self_healing                                                 0 [0, 1]                        ""
    is_other_healing                                                0 [0, 1]                        ""
    is_self_buffing                                                 0 [0, 1]                        ""
    is_other_buffing                                                0 [0, 1]                        ""
    is_weapon                                                       0 [0, 1]                        ""
    is_known                                                        0 [0, 1]                        ""
    is_safe                                                         1 [0, 1]                        ""
    is_consumed                                                     0 [0, 1]                        ""
    ranged_min_distance                                             0 [0, 1]                        ""

ItemActionComponent
 - Members -----------------------------
    action_id                                                       -                               "the name ID of the action"

ItemAlchemyComponent

ItemChestComponent
 - Members -----------------------------
    item_count_min                                                  0 [0, 1e+006]                   ""
    item_count_max                                                  0 [0, 1e+006]                   ""
    level                                                           0 [0, 1e+006]                   ""
    enemy_drop                                                      0 [0, 1]                        "enemy_drop, if set will modify the item_count_min, item_count_max..."
    actions                                                         -                               "e.g. 'bullet,bullet,damage' ... actions are parsed into a string"
    action_uses_remaining                                           -                               "e.g. '10,10,-1' ... action uses remaining counts are parsed into a string"
    other_entities_to_spawn                                         -                               "file names of other entities we should spawn from this chest, comma separated"
    mSeed                                                           0 [0, 1]                        "this is used to figure out what we spawn from this chest"

ItemComponent
 - Members -----------------------------
    item_name                                                       -                               "the name of the item"
    is_stackable                                                    0 [0, 1]                        "does this item stack on other items the same 'item_name' in the inventory?"
    is_consumable                                                   0 [0, 1]                        "if 1, using this item will reduce 'uses_remaining'. When it reaches zero the item is destroyed"
    auto_pickup                                                     0 [0, 1]                        "if 1, item will be automatically picked up, no pickup hint is shown"
    permanently_attached                                            0 [0, 1]                        "if 1, this item can't be removed from a container once it is put inside one"
    uses_remaining                                                  -1 [0, 1]                       "how many times can this item be used?"
    is_identified                                                   1 [0, 1]                        "is it known what this item does?"
    is_frozen                                                       0 [0, 1]                        "if 1, this item can't be modified or moved from a wand"
    collect_nondefault_actions                                      0 [0, 1]                        "does player keep this item when respawning?"
    remove_on_death                                                 0 [0, 1]                        "is this entity destroyed when it's in an inventory and the inventory owner dies?"
    remove_on_death_if_empty                                        0 [0, 1]                        "is this entity destroyed when it's in an inventory, empty and the inventory owner dies?"
    remove_default_child_actions_on_death                           0 [0, 1]                        "if true, the default AbilityComponent.child_actions in this items will be removed when it dies"
    play_hover_animation                                            0 [0, 1]                        "if 1, the item will play a hovering animation"
    play_spinning_animation                                         1 [0, 1]                        "if 1, the item will play a spinning animation, if player_hover_animation is 0"
    is_equipable_forced                                             0 [0, 1]                        "if 1, the default logic for determining if an item can be equiped in inventory is overridden and this can be always equipped"
    play_pick_sound                                                 1 [0, 1]                        "if 1, plays a default sound when picked"
    max_child_items                                                 0 [0, 1]                        "number of items this can hold inside itself. TODO: get rid of all uses of 'ability->gun_config.deck_capacity' and replace them with this!"
    ui_sprite                                                       -                               "sprite displayed for the item in various UIs. If not empty overrides sprites declared by Ability and ItemAction"
    ui_description                                                  -                               "item description displayed in various UIs"
    enable_orb_hacks                                                0 [0, 1]                        ""
    is_all_spells_book                                              0 [0, 1]                        ""
    next_frame_pickable                                             0 [0, 1]                        ""
    is_pickable                                                     1 [0, 1]                        "can this be picked up and placed on someone's inventory"
    is_hittable_always                                              0 [0, 1]                        "to override the weirdness that is is_pickable, which affects if this is hittable or not. If true, will always be hittable regardless of is_pickable"
    item_pickup_radius                                              14.1 [0, 1]                     "how many pixels away can this item be picked up from"
    camera_max_distance                                             50 [0, 1]                       "how far can we move the camera from the player when this item is equipped"
    has_been_picked_by_player                                       0 [0, 1]                        ""
    mFramePickedUp                                                  0 [0, 1]                        ""
 - Privates -----------------------------
    mItemUid                                                        0 [0, 1]                        ""
    mIsIdentified                                                   1 [0, 1]                        ""

ItemCostComponent
 - Members -----------------------------
    cost                                                            100 [0, 3500]                   ""
    stealable                                                       0 [0, 1]                        "if set - will check that it's within an area called shop"
 - Privates -----------------------------
    mExCost                                                         -1 [0, 1]                       "used to change the text on the sprite"

ItemPickUpperComponent
 - Members -----------------------------
    is_in_npc                                                       0 [0, 1]                        ""
    is_immune_to_kicks                                              0 [0, 1]                        "if set, won't drop the wand if kicked. Mainly used by wand ghosts."

ItemRechargeNearGroundComponent
 - Members -----------------------------
    TEMP_TEMPY                                                      0 [0, 3.5]                      ""
    TEMP_TEMP_TEMP                                                  0 [0, 3.5]                      ""

ItemStashComponent
 - Members -----------------------------
    throw_openable_cooldown_frames                                  30 [0, 180]                     ""
    init_children                                                   1 [0, 1]                        ""
 - Privates -----------------------------
    mNextFrameOpenable                                              0 [0, 1]                        ""
    mFrameOpened                                                    -1 [0, 1]                       ""

KickComponent
 - Members -----------------------------
    kick_radius                                                     3 [0, 3.5]                      ""

LevitationComponent
 - Members -----------------------------
    radius                                                          20 [1, 50]                      "the radius in which we look for entities / bodies to float"
    entity_force                                                    0.3 [0, 1]                      "how much do we apply the mouse movements to the entitiy"
    box2d_force                                                     0.3 [0, 1]                      "how much do we apply the mouse movements to the entitiy"
    effect_lifetime_frames                                          600 [1, 600]                    ""

LifetimeComponent
 - Members -----------------------------
    lifetime                                                        -1 [0, 1]                       "if anything else than -1 will kill this entity when this many frames have passed"
 - Privates -----------------------------
    creation_frame                                                  0 [0, 1]                        "we'll set this to GG.GetFrameNum() when this component is created"
    kill_frame                                                      0 [0, 1]                        "frame that this is killed at"
    render_physics_blink                                            0 [0, 1]                        "if 1, and the entity has a physicsbody, the body blinks when the lifetime is running out"

LightComponent
 - Members -----------------------------
    update_properties                                               0 [0, 1]                        "turn this on if you expect this to function like the other components"
    radius                                                          0 [0, 3000]                     "The radius of the light in world pixels."
    r                                                               255 [0, 255]                    "Color red 0-255"
    g                                                               178 [0, 255]                    "Color green 0-255"
    b                                                               118 [0, 255]                    "Color blue 0-255"
    offset_x                                                        0 [-3000, 3000]                 "Offset from the center of entity."
    offset_y                                                        0 [-3000, 3000]                 "Offset from the center of entity."
    fade_out_time                                                   0 [0, 5]                        "time in seconds, if not 0, this is how long this takes to die, when the component is destroyed"
    blinking_freq                                                   1 [0, 1]                        "if less than 1, will blink randomly when rand() < blinking_freq"
 - Privates -----------------------------
    mAlpha                                                          1 [0, 1]                        ""
    mSprite                                                         -                               ""

LightningComponent
 - Members -----------------------------
    sprite_lightning_file                                           data/particles/lightning_ray.png [0, 1] "particle effect, from where the file is loaded that lightning is generated from"
    is_projectile                                                   0 [0, 1]                        "if this is true, it's a projectile lightning and looks for ProjectileComponent and uses the data from there to move it"
    explosion_type                                                  1 [0, 1]                        "1 = lightning trail"
    arc_lifetime                                                    60 [0, 1]                       "remaining number of frames the arc exists"
 - Objects -----------------------------
    config_explosion                                                -                               ""
 - Privates -----------------------------
    mExPosition                                                     -                               "stores the ex position of this entity"
    mArcTarget                                                      0 [0, 1]                        "if 'mArcTarget' points to an existing entity a lighting arc will be created between this entity and 'mArcTarget'"

LimbBossComponent
 - Members -----------------------------
    state                                                           0 [0, 1]                        ""
 - Privates -----------------------------
    mStatePrev                                                      -1 [0, 1]                       ""
    mMoveToPositionX                                                0 [0, 1]                        ""
    mMoveToPositionY                                                0 [0, 1]                        ""

LiquidDisplacerComponent
 - Members -----------------------------
    radius                                                          1 [0, 20]                       ""
    velocity_x                                                      30 [0, 100]                     ""
    velocity_y                                                      30 [0, 100]                     ""
 - Privates -----------------------------
    mPrevX                                                          0 [0, 1]                        ""
    mPrevY                                                          0 [0, 1]                        ""

LoadEntitiesComponent
 - Members -----------------------------
    entity_file                                                     -                               "path to the entity file we should load"
    kill_entity                                                     1 [0, 1]                        "if 1, we kill our entity when it is created"
    timeout_frames                                                  0 [0, 180]                      "for timer"
    mTimerTriggerFrame                                              -1 [0, 1]                       ""

LocationMarkerComponent
 - Members -----------------------------
    id                                                              0 [0, 3]                        ""

LooseGroundComponent
 - Members -----------------------------
    probability                                                     0 [0, 1]                        "how often do we do this... shoots a ray in random direction and does the loosening"
    max_durability                                                  2147483647 [0, 1]               "if material durability > max_durability, it is not loosened"
    max_distance                                                    256 [0, 1]                      "how far raytraces to find things to loosen up"
    max_angle                                                       1.57 [0, 1]                     "how much raytraces go to different directions around the up-vector. pi=full circle"
    min_radius                                                      3 [0, 1]                        "the minimum radius of our loosening of pixels"
    max_radius                                                      8 [0, 1]                        "the maximum radius of our loosening of pixels"
    chunk_probability                                               0 [0, 1]                        "if > 0, will drop box2d chunks of the ceiling"
    chunk_max_angle                                                 0.7 [0, 1]                      "how much raytraces go to different directions around the up-vector. pi=full circle"
    chunk_count                                                     -1 [0, 1]                       "how many chunks are we allowed to do, -1 = infinite"
    collapse_images                                                 data/collapse_masks/big/$[0-14].png [0, 1] "loads these files randomly to do the collapse shapes"
 - Privates -----------------------------
    mChunkCount                                                     0 [0, 1]                        "how many chunks are we allowed to do, -1 = infinite"

LuaComponent
 - Members -----------------------------
    script_source_file                                              -                               ""
    execute_on_added                                                0 [0, 1]                        ""
    execute_on_removed                                              0 [0, 1]                        ""
    execute_every_n_frame                                           1 [1, 150]                      "1 = execute every frame. 2 = execute every second frame. 3 = execute every third frame etc. -1 or > 10000 is forever"
    execute_times                                                   0 [0, 1]                        "How many times should the script be executed? < 1 means infinite"
    remove_after_executed                                           0 [0, 1]                        ""
    enable_coroutines                                               0 [0, 1]                        ""
    script_damage_received                                          -                               "if set, calls function 'damage_received( float damage, string message, int entity_thats_responsible, bool is_fatal  )' when we receive a message about damage (Message_DamageReceived)"
    script_item_picked_up                                           -                               "if set, calls function 'item_pickup( int entity_item, int entity_pickupper, string item_name )' when message 'Message_ItemPickUp' is called"
    script_shot                                                     -                               "if set, calls function 'shot( projectile_entity_id )' when we receive Message_Shot"
    script_collision_trigger_hit                                    -                               "if set, calls function 'collision_trigger_hit( colliding_entity_id )' when we receive Message_CollisionTriggerHit"
    script_collision_trigger_timer_finished                         -                               "if set, calls function 'collision_trigger_timer_finished()' when we receive Message_CollisionTriggerTimerFinished"
    script_physics_body_modified                                    -                               "if set, calls function 'physics_body_modified( is_destroyed )' when physics body has been modified"
    script_pressure_plate_change                                    -                               "if set, calls function 'pressure_plate_change( new_state )' when PressurePlateComponent decides that things have change"
    script_inhaled_material                                         -                               "if set, calls function 'inhaled_material( material_name, count )' once per second for each inhaled material"
    script_ingested_material                                        -                               "if set, calls function 'ingested_material( material_name, count )' once per second for each ingested material"
    script_death                                                    -                               "if set, calls function 'death( int damage_type_bit_field, string damage_message, int entity_thats_responsible, bool drop_items )' when we receive message Message_Death"
    script_throw_item                                               -                               "if set, calls function 'throw_item( from_x, from_y, to_x, to_y )' when we receive message Message_ThrowItem"
    script_material_area_checker_failed                             -                               "if set, calls function 'material_area_checker_failed( pos_x, pos_y, )' when we receive message Message_MaterialAreaCheckerFailed"
    script_material_area_checker_success                            -                               "if set, calls function 'material_area_checker_success( pos_x, pos_y, )' when we receive message Message_MaterialAreaCheckerSuccess"
    script_electricity_receiver_switched                            -                               "if set, calls function 'electricity_receiver_switched( bool is_electrified )' when we receive message Message_ElectricityReceiverSwitched"
    mLastExecutionFrame                                             -1 [0, 1]                       ""
 - Privates -----------------------------
    mNextExecutionTime                                              -1 [0, 1]                       ""
    mTimesExecuted                                                  0 [0, 1]                        ""
    mLuaManager                                                     -                               ""
    mPersistentValues                                               -                               ""

MagicConvertMaterialComponent
 - Members -----------------------------
    radius                                                          256 [0, 512]                    ""
    is_circle                                                       0 [0, 1]                        ""
    steps_per_frame                                                 10 [0, 512]                     ""
    from_material_tag                                               -                               "the tag of material, e.g. [liquid]"
    from_any_material                                               0 [0, 1]                        "if 1, converts any cells of any material to 'to_materia'"
    clean_stains                                                    0 [0, 1]                        ""
    extinguish_fire                                                 0 [0, 1]                        ""
    loop                                                            0 [0, 1]                        ""
    kill_when_finished                                              1 [0, 1]                        ""
    convert_entities                                                0 [0, 1]                        "if 1, kills entities with a damagemodel and converts them to 'to_material'"
    stain_frozen                                                    0 [0, 1]                        "petri hax"
    mRadius                                                         0 [0, 512]                      ""

MagicXRayComponent
 - Members -----------------------------
    radius                                                          256 [0, 512]                    ""
    steps_per_frame                                                 10 [0, 512]                     ""
    mStep                                                           0 [0, 1]                        ""
    mRadius                                                         0 [0, 1]                        ""

ManaReloaderComponent

MaterialAreaCheckerComponent
 - Members -----------------------------
    update_every_x_frame                                            0 [0, 1]                        "if something other than 0 or 1, will only update_every_x_frames "
    look_for_failure                                                1 [0, 1]                        "if true, will send message Message_MaterialAreaCheckerFailed if the material doesn't exist. If false, will send a message Message_MaterialAreaCheckerSuccess if the aabb is full of material and material2"
    kill_after_message                                              1 [0, 1]                        "will kill this entity after sending the message"
 - Privates -----------------------------
    mPosition                                                       0 [0, 1]                        "keeps track where we are"
    mLastFrameChecked                                               0 [0, 1]                        "keeps track of how often we've checked"

MaterialComponent
 - Members -----------------------------
    material_name                                                   -                               ""
    material_index                                                  10 [-100, 100]                  ""
    material_min                                                    0.1 [0, 3.5]                    ""
    material_max                                                    0.1 [0, 3.5]                    ""
    add_perlin                                                      0 [0, 1]                        ""
    add_perlin_scale_x                                              1 [0, 1]                        ""
    add_perlin_scale_y                                              1 [0, 1]                        ""
    is_rare                                                         0 [0, 1]                        ""
    limit_y                                                         0 [0, 1]                        ""
    limit_min_y                                                     100 [-1024, 2048]               ""
    limit_max_y                                                     2048 [-1024, 2048]              ""
    rare_use_perlin                                                 0 [0, 1]                        ""
    rare_use_fbm_perlin                                             0 [0, 1]                        ""
    rare_use_polka                                                  1 [0, 1]                        ""
    rare_scale_x                                                    0.05 [0, 0.05]                  ""
    rare_scale_y                                                    0.05 [0, 0.05]                  ""
    rare_polka_radius_low                                           0.2 [0, 1]                      ""
    rare_polka_radius_high                                          0.65 [0, 1]                     ""
    rare_polka_is_boxed                                             1 [0, 1]                        ""
    rare_polka_probability                                          0.2 [0, 1]                      ""
    rare_required_min                                               0.2 [-1, 1]                     ""
    rare_required_max                                               1 [-1, 1]                       ""
    is_polygon                                                      0 [0, 1]                        "if true, uses points inside polygon to determine if this material is placed "
 - Privates -----------------------------
    celldata                                                        -                               ""

MaterialInventoryComponent
 - Members -----------------------------
    drop_as_item                                                    1 [0, 1]                        "if true, drops a bag that the player can big up"
    on_death_spill                                                  0 [0, 1]                        "if true, on the death this will explode all the materials into air"
    leak_on_damage_percent                                          0 [0, 1]                        "if higher than 0 then it might leak when projectile damage happens"
    leak_pressure_min                                               0.7 [0, 1]                      "leak pressure coefficient"
    leak_pressure_max                                               1.1 [0, 1]                      "leak pressure coefficient"
    min_damage_to_leak                                              0.09 [0, 1]                     "the minimum damage that has to be done in order for a leak to occur"
    b2_force_on_leak                                                0 [0, 10]                       "if 0, nothing happens, elsewise will add a b2 force to the particleemitter which will push the b2body"
    death_throw_particle_velocity_coeff                             1 [0, 1]                        "how far do we throw material particles on death?"
    kill_when_empty                                                 0 [0, 1]                        "if set, will send MessageDeath when materials are drained"
    halftime_materials                                              0 [0, 1]                        "if true, will multiply the materials with the given halftimes"
    max_capacity                                                    -1 [0, 1]                       "how much materials we can store in total. < 0 = infinite"
    audio_collision_size_modifier_amount                            0 [0, 1]                        "if > 0, 'fullness of this container' * 'audio_collision_size_modifier_amount' is added to collision audio event size"
 - Privates -----------------------------
    is_death_handled                                                0 [0, 1]                        ""

MaterialSeaSpawnerComponent
 - Members -----------------------------
    speed                                                           10 [1, 100]                     "How many pixels to cover per one direction per one frame"
    sine_wavelength                                                 10 [0, 2]                       "Parameters for sine wave that affects material spawn pattern"
    sine_amplitude                                                  5 [0, 2]                        "Parameters for sine wave that affects material spawn pattern"
    noise_scale                                                     0.1 [0, 1]                      "Parameters for noise that affects material spawn pattern"
    noise_threshold                                                 0.05 [0, 1]                     "Parameters for noise that affects material spawn pattern"
    m_position                                                      0 [0, 1]                        ""
    frames_run                                                      0 [0, 1]                        "to help keep the effect"

MaterialSuckerComponent
 - Members -----------------------------
    material_type                                                   0 [0, 3]                        "what's the type of cells that we suck (liquid, sand...)"
    barrel_size                                                     50 [0, 1024]                    "how many pixels can we suck up"
    num_cells_sucked_per_frame                                      1 [0, 5]                        "How many cells at max can we suck per frame?"
    set_projectile_to_liquid                                        0 [0, 1]                        "if set, will set the projectile what ever we're sucking...?"
    last_material_id                                                0 [0, 1]                        "hax... this is set if we use set_projectile_to_liquid"
    suck_gold                                                       0 [0, 1]                        "if set will just suck gold and update wallet"
    suck_health                                                     0 [0, 1]                        "if set will just suck healthium material and add 1 hp every sucked healthium"
    mAmountUsed                                                     0 [0, 1]                        "how full are we"
 - Privates -----------------------------
    mGoldAccumulator                                                0 [0, 1]                        "accumulates amount of gold picked during consecutive frames"
    mLastFramePickedGold                                            -2 [0, 1]                       "last frame we picked gold"

MoveToSurfaceOnCreateComponent
 - Members -----------------------------
    lookup_radius                                                   64 [0, 64]                      ""
    offset_from_surface                                             2 [0, 10]                       ""
    ray_count                                                       4 [0, 8]                        ""
    verlet_min_joint_distance                                       32 [0, 128]                     ""

MusicEnergyAffectorComponent
 - Members -----------------------------
    energy_target                                                   0.5 [0, 1]                      "the energy this makes music go towards"
    fade_range                                                      0 [0, 256]                      "if > 0, fade between 0 and energy_target based on distance to this entity"
    trigger_danger_music                                            1 [0, 1]                        "if 1, attempts to trigger danger music no matter what energy level is reached"
    fog_of_war_threshold                                            200 [0, 255]                    "if fog of war at position of this entity is greater than 'fog_of_war_threshold', this has  no effect"
    is_enemy                                                        1 [0, 1]                        ""
    energy_lerp_up_speed_multiplier                                 0 [0, 1]                        ""

NinjaRopeComponent
 - Members -----------------------------
    max_length                                                      356 [0, 2000]                   ""
    mLength                                                         0 [0, 2000]                     ""
 - Privates -----------------------------
    mSegments                                                       -                               ""

OrbComponent
 - Members -----------------------------
    orb_id                                                          0 [0, 20]                       "must be unique for every orb in the world"

ParticleEmitterComponent
 - Members -----------------------------
    emitted_material_name                                           blood [0, 1]                    ""
    create_real_particles                                           0 [0, 1]                        "used to be emit_real_particles - creates these particles in the grid, if that happens velocity and lifetime are ignored"
    emit_real_particles                                             0 [0, 1]                        "this creates particles that will behave like particles, but work outside of the screen"
    emit_cosmetic_particles                                         0 [0, 1]                        "particle does have collisions, but no other physical interactions with the world. the particles are culled outside camera region"
    cosmetic_force_create                                           1 [0, 1]                        "cosmetic particles are created inside grid cells"
    render_back                                                     1 [0, 1]                        "for cosmetic particles, if they are rendered on front or in the back..."
    collide_with_grid                                               1 [0, 1]                        "for cosmetic particles, if 1 the particles collide with grid and only exist in screen space"
    collide_with_gas_and_fire                                       1 [0, 1]                        "does it collide with gas and fire, works with create_real_particles and raytraced images "
    particle_single_width                                           1 [0, 1]                        "for cosmetic particles, forces them (gas,fire) to be only 1 pixel wide "
    emitter_lifetime_frames                                         -1 [0, 1]                       "emitter lifetime in frames. -1 = infinite"
    fire_cells_dont_ignite_damagemodel                              0 [0, 1]                        "if set, and fire cells are created, this changes their default behaviour of igniting DamageModels"
    x_pos_offset_min                                                0 [-20, 20]                     ""
    y_pos_offset_min                                                0 [-20, 20]                     ""
    x_pos_offset_max                                                0 [-20, 20]                     ""
    y_pos_offset_max                                                0 [-20, 20]                     ""
    area_circle_sector_degrees                                      360 [0, 360]                    ""
    x_vel_min                                                       0 [-100, 100]                   ""
    x_vel_max                                                       0 [-100, 100]                   ""
    y_vel_min                                                       0 [-100, 100]                   ""
    y_vel_max                                                       0 [-100, 100]                   ""
    direction_random_deg                                            0 [0, 90]                       ""
    velocity_always_away_from_center                                0 [-256, 256]                   "if set, will make the velocity's rotation always away from center of randomized aabb"
    lifetime_min                                                    5 [0, 10]                       ""
    lifetime_max                                                    10 [0, 10]                      ""
    airflow_force                                                   0 [0, 6]                        ""
    airflow_time                                                    1 [0, 2]                        ""
    airflow_scale                                                   1 [0, 2]                        ""
    friction                                                        0 [0, 10]                       ""
    attractor_force                                                 0 [0, 100]                      "If > 0, an attractor is created at the position of the entity that owns this component"
    count_min                                                       1 [0, 10]                       ""
    count_max                                                       3 [0, 10]                       ""
    emission_interval_min_frames                                    5 [0, 120]                      ""
    emission_interval_max_frames                                    10 [0, 120]                     ""
    emission_chance                                                 100 [0, 100]                    ""
    delay_frames                                                    0 [0, 1]                        "if set will delay this many frames until starts"
    is_emitting                                                     1 [0, 1]                        ""
    use_material_inventory                                          0 [0, 1]                        "if set, it'll use MaterialInventoryComponent as the source of the particles emitted"
    is_trail                                                        0 [0, 1]                        "if set, will do a trail based on the previous position and current position"
    trail_gap                                                       0 [0, 1]                        "if > 0, trail particles will be generated this far from each other between our old and new position, else [count_min-count_max] particles will be generated on the line"
    render_on_grid                                                  0 [0, 1]                        "if set, particle render positions will be snapped to cell grid"
    fade_based_on_lifetime                                          0 [0, 1]                        "if set, particle's position in its lifetime will determine the rendering alpha"
    draw_as_long                                                    0 [0, 1]                        "if set, particle will rendered as a trail along it's movement vector"
    b2_force                                                        0 [0, 10]                       "if 0 nothing happens, if 1 will apply a force to the physics body (if has one), also requires that we use the material inventory"
    set_magic_creation                                              0 [0, 1]                        "if set will set the magic creation 1 in the cells and do the white glow effect"
    image_animation_file                                            -                               "file to use for image-based animation"
    image_animation_colors_file                                     -                               "file to use for image-based animation"
    image_animation_speed                                           1 [0, 255]                      "how long do we stay on one frame of image-based animation. 0.5 means two game frames per one animation frame. 2.0 means two animation frames per one game frame, and so on. 0 means we always emit at time 0 of the animation."
    image_animation_loop                                            1 [0, 1]                        "does image-based animation keep looping while this component is active?"
    image_animation_phase                                           0 [0, 1]                        "the point in time [0,1] where the image-based animation will start the first cycle"
    image_animation_emission_probability                            1 [0, 1]                        "[0,1], probability of emitting image based particles is multiplied with this"
    image_animation_raytrace_from_center                            0 [0, 1]                        "enable this to disable image_animations (from the center) going through the world"
 - Privates -----------------------------
    mExPosition                                                     -                               "is used with is_trail"
    mMaterialInventoryMax                                           1024 [0, 1]                     "this is how we figure out the pressure, when using material_inventory"
    m_material_id                                                   0 [0, 1]                        ""
    m_next_emit_frame                                               0 [0, 1]                        ""
    m_has_emitted                                                   0 [0, 1]                        ""
    m_last_emit_position                                            -                               ""
    m_cached_image_animation                                        -                               ""
    m_image_based_animation_time                                    0 [0, 1]                        ""
    m_collision_angles                                              -                               ""
    m_particle_attractor_id                                         -1 [0, 1]                       ""

PathFindingComponent
 - Members -----------------------------
    search_depth_max_no_goal                                        20 [0, 1e+006]                  "TODO: Comment"
    iterations_max_no_goal                                          1500 [0, 1e+006]                "TODO: Comment"
    search_depth_max_with_goal                                      2500 [0, 1e+006]                "TODO: Comment"
    iterations_max_with_goal                                        1500 [0, 1e+006]                "TODO: Comment"
    cost_of_flying                                                  20 [0, 100000]                  "TODO: Comment"
    distance_to_reach_node_x                                        2 [0, 200]                      "TODO: Comment"
    distance_to_reach_node_y                                        6 [0, 200]                      "TODO: Comment"
    frames_to_get_stuck                                             60 [0, 600]                     "TODO: Comment"
    frames_between_searches                                         30 [0, 300]                     "TODO: Comment"
    y_walking_compensation                                          0 [-100, 100]                   "TODO: Comment"
    can_fly                                                         1 [0, 1]                        "TODO: Comment"
    can_walk                                                        1 [0, 1]                        "TODO: Comment"
    can_jump                                                        0 [0, 1]                        "TODO: Comment"
    can_dive                                                        0 [0, 1]                        "TODO: Comment"
    can_swim_on_surface                                             0 [0, 1]                        "TODO: Comment"
    never_consider_line_of_sight                                    0 [0, 1]                        "if 1, we require a path to have an entity at the goal, having line of sight to the entity is not enough"
    space_required                                                  0 [0, 20]                       "how far (in cells) must a point on our route be from the nearest wall to consider it passable?"
    max_jump_distance_from_camera                                   400 [0, 400]                    "TODO: Comment"
    jump_speed                                                      200 [0, 1000]                   "TODO: Comment"
    initial_jump_lob                                                1 [0, 5]                        "TODO: Comment"
    initial_jump_max_distance_x                                     100 [0, 1000]                   "TODO: Comment"
    initial_jump_max_distance_y                                     80 [0, 1000]                    "TODO: Comment"
 - Privates -----------------------------
    input                                                           -                               "TODO: Comment"
    job_result_receiver                                             -                               "TODO: Comment"
    waiting_for                                                     0 [0, 1]                        "TODO: Comment"
    next_search_frame                                               0 [0, 1]                        "TODO: Comment"
    path                                                            -                               "TODO: Comment"
    path_next_node                                                  -                               "TODO: Comment"
    path_next_node_vector_to                                        -                               "TODO: Comment"
    path_next_node_distance_to                                      0 [0, 1]                        "TODO: Comment"
    path_previous_node                                              -                               "TODO: Comment"
    path_frames_stuck                                               0 [0, 1]                        "TODO: Comment"
    path_is_stuck                                                   0 [0, 1]                        "TODO: Comment"
    path_last_frame_with_job                                        0 [0, 1]                        "TODO: Comment"
    mLogic                                                          -                               "this defines what is an acceptable path"
    mFallbackLogic                                                  -                               "we use this to define an acceptable path if mLogic doesn't return one"
    mSelectedLogic                                                  -                               "TODO: Comment"
    mEnabled                                                        0 [0, 1]                        "TODO: Comment"
    mState                                                          -                               "TODO: Comment"
    mTimesStuck                                                     0 [0, 1]                        "TODO: Comment"
    mNextClearDontApproachListFrame                                 0 [0, 1]                        "TODO: Comment"
    mNodeProximityCheckCorrectionY                                  0 [0, 1]                        "TODO: Comment"
    debug_path                                                      -                               "TODO: Comment"
    jump_velocity_multiplier                                        -                               "TODO: Comment"

PathFindingGridMarkerComponent
 - Members -----------------------------
    marker_work_flag                                                0 [0, 255]                      ""
    marker_offset_x                                                 0 [-1000, 1000]                 ""
    marker_offset_y                                                 0 [-1000, 1000]                 ""
    player_marker_radius                                            0 [0, 128]                      ""
 - Privates -----------------------------
    mNode                                                           -                               "we change the work state of this node. thus we need to keep a reference to it"

PhysicsAIComponent
 - Members -----------------------------
    target_vec_max_len                                              5 [0, 1]                        ""
    force_coeff                                                     30 [0, 1]                       ""
    force_balancing_coeff                                           1.5 [0, 1]                      ""
    force_max                                                       100 [0, 1]                      ""
    torque_coeff                                                    50 [0, 1]                       ""
    torque_balancing_coeff                                          0.2 [0, 1]                      ""
    torque_max                                                      50 [0, 1]                       ""
    damage_deactivation_probability                                 80 [0, 1]                       ""
    damage_deactivation_time_min                                    30 [0, 1]                       ""
    damage_deactivation_time_max                                    60 [0, 1]                       ""
    die_on_remaining_mass_percentage                                0.3 [0, 1]                      ""
    levitate                                                        1 [0, 1]                        ""
    keep_inside_world                                               1 [0, 1]                        "fix to the bug in which the spiders spawned inside the holy mountain, if set will try not to go into places which aren't loaded "
    free_if_static                                                  0 [0, 1]                        "set true for the boss, because box2d might turn this body into a static body, if it thinks it's glitching out. "
 - Privates -----------------------------
    rotation_speed                                                  0 [0, 1]                        ""
    mStartingMass                                                   1 [0, 1]                        ""
    mMainBodyFound                                                  0 [0, 1]                        ""
    mNextFrameActive                                                0 [0, 1]                        ""
    mRotationTarget                                                 0 [0, 1]                        ""
    mLastPositionWhenHadPath                                        -                               ""
    mHasLastPosition                                                0 [0, 1]                        ""

PhysicsBodyCollisionDamageComponent
 - Members -----------------------------
    speed_threshold                                                 60 [0, 100]                     ""
    damage_multiplier                                               0.016667 [0, 1]                 ""

PhysicsBodyComponent
 - Members -----------------------------
    is_external                                                     0 [0, 1]                        "if mBody is set from outside, will ignore all the things"
    hax_fix_going_through_ground                                    0 [0, 1]                        "if set will lift the body upwards if it is inside ground"
    hax_fix_going_through_sand                                      0 [0, 1]                        "hax_fix_going_through_ground has to be set, if set will lift the body upwards if it is inside sand"
    hax_wait_till_pixel_scenes_loaded                               0 [0, 1]                        ""
    uid                                                             0 [0, 1000]                     "if the entity has multiple physics bodies and has specific shapes for those and possible joints, you should use this. 0 is default for shapes"
    is_enabled                                                      1 [0, 1]                        "Use this to kill the physics body of. if is_enabled is set to false, will destroy the physics body"
    linear_damping                                                  0 [0, 1]                        ""
    angular_damping                                                 0 [0, 1]                        ""
    allow_sleep                                                     1 [0, 1]                        ""
    fixed_rotation                                                  0 [0, 1]                        ""
    buoyancy                                                        0.7 [0, 1]                      ""
    is_bullet                                                       0 [0, 1]                        ""
    is_static                                                       0 [0, 1]                        ""
    is_kinematic                                                    0 [0, 1]                        ""
    is_character                                                    0 [0, 1]                        "if it is a character, then we need to few interesting things from time to time"
    go_through_sand                                                 0 [0, 1]                        "if set, will go through sand PhysicsBridge::mGoThroughSand = 1"
    gridworld_box2d                                                 1 [0, 1]                        "default is 1. You should only change this if you know the body isn't going to touch gridworld"
    auto_clean                                                      1 [0, 1]                        "if set, the simulation might destroy this body if it's hidden under sand. Problematic if you have a small piece with joint attached to something like the wheels of minecart. Set to 0 in cases like that"
    on_death_leave_physics_body                                     0 [0, 1]                        "if set, will leave the b2body into the world, even if the entity is killed"
    on_death_really_leave_body                                      0 [0, 1]                        "camera bound... god damn... we need something special when we want to leave the body"
    update_entity_transform                                         1 [0, 1]                        "WARNING! Don't touch this unless you know what you're doing. If false, doesn't update the entitys transform to match the physics body. This is used with multi body entities, to use the correct body to update the entity, e.g. minecart"
    force_add_update_areas                                          0 [0, 1]                        "if 1, we will mark our predicted aabb as a box2d update area."
    kills_entity                                                    1 [0, 1]                        "if set, will kill the entity when physics body is destroyed"
    randomize_init_velocity                                         0 [0, 1]                        "randomizes the init velocity"
    mActiveState                                                    0 [0, 1]                        "private variable, please don't mess around with this"
 - Privates -----------------------------
    mBody                                                           -                               ""
    mBodyId                                                         0 [0, 1]                        "this is mBody->GetBodyId() - not to be confused with uid shit, has to be tracked separately, since the mBody pointer is not unique"
    mPixelCount                                                     0 [0, 1]                        "if set, tracks the number of csolidcells the body has"
    mLocalPosition                                                  -                               ""
    mRefreshed                                                      0 [0, 1]                        "this is sure the bodies are only parsed once"

PhysicsImageShapeComponent
 - Members -----------------------------
    body_id                                                         0 [0, 1000]                     "which body is this attached to, uses body uid, 0 is default for both"
    use_sprite                                                      0 [0, 1]                        "will try to find the SpriteComponent and use that"
    is_circle                                                       0 [0, 1]                        "tries to fit this into a circle, looks at bounding box of the pixels and sets the circle to the center of that with radius being the line from there to a straight edge"
    centered                                                        0 [0, 1]                        "if this is true, moves offset to be in the center of the image, overwrites the offset_x, offset_y"
    offset_x                                                        0 [0, 1]                        "offset x in pixels"
    offset_y                                                        0 [0, 1]                        "offset y in pixels"
    z                                                               0 [0, 1]                        "offset in the z direction"
    image_file                                                      -                               "the png file from which the body is created from"

PhysicsJointComponent
 - Members -----------------------------
    nail_to_wall                                                    0 [0, 1]                        ""
    grid_joint                                                      0 [0, 1]                        "if set, will do a grid joint that tracks which part of the body is it when the body is destroyed / chipped away"
    breakable                                                       0 [0, 1]                        "if set will break if theres a force too strong"
    body1_id                                                        0 [0, 1]                        ""
    body2_id                                                        0 [0, 1]                        ""
    pos_x                                                           0 [0, 3.5]                      ""
    pos_y                                                           0 [0, 3.5]                      ""
    delta_x                                                         0 [-10, 10]                     "For mouse joint only ... moves the mouse joint by *dt "
    delta_y                                                         0 [-10, 10]                     "For mouse joint only ... moves the mouse joint by *dt "
    mMotorEnabled                                                   0 [0, 1]                        "enable motor, by setting this to true"
    mMotorSpeed                                                     0 [0, 20]                       "if enabled this gets set to speed"
    mMaxMotorTorque                                                 1 [0, 1]                        "max torque for motor"
 - Privates -----------------------------
    mJoint                                                          -                               ""

PhysicsPickUpComponent
 - Members -----------------------------
    pick_up_strength                                                200 [0, 1]                      ""
 - Privates -----------------------------
    isBroken                                                        0 [0, 1]                        ""
    leftJointPos                                                    -                               ""
    rightJointPos                                                   -                               ""
    leftJoint                                                       -                               ""
    rightJoint                                                      -                               ""

PhysicsRagdollComponent
 - Members -----------------------------
    filename                                                        -                               "file that should include just a list of other files, that have all the parts"
    filenames                                                       -                               "a list of body parts as png images, separate the files by ','. e.g. 'data/temp/ragdoll/leg.png, data/temp/ragdoll/head.png,...'"
    offset_x                                                        0 [0, 20]                       "offset of where the ragdoll will be created"
    offset_y                                                        0 [0, 20]                       "offset of where the ragdoll will be created"
 - Privates -----------------------------
    bodies                                                          -                               ""

PhysicsShapeComponent
 - Members -----------------------------
    recreate                                                        0 [0, 1]                        ""
    is_circle                                                       0 [0, 1]                        ""
    is_box                                                          1 [0, 1]                        ""
    is_capsule                                                      0 [0, 1]                        ""
    is_based_on_sprite                                              0 [0, 1]                        "if set, will use sprite component to figure out a box that fits this"
    friction                                                        0.75 [0, 1]                     ""
    restitution                                                     0.1 [0, 1]                      ""
    density                                                         0.75 [0, 5]                     ""
    local_position_x                                                0 [-5, 5]                       ""
    local_position_y                                                0 [-5, 5]                       ""
    radius_x                                                        1 [0, 10]                       ""
    radius_y                                                        1 [0, 10]                       ""
    capsule_x_percent                                               0.25 [0, 1]                     ""
    capsule_y_percent                                               0.3 [0, 1]                      ""

PhysicsThrowableComponent
 - Members -----------------------------
    throw_force_coeff                                               1 [0, 2]                        ""
    max_throw_speed                                                 180 [0, 256]                    ""
    min_torque                                                      0.5 [0, 20]                     ""
    max_torque                                                      8 [0, 20]                       ""
    tip_check_offset_min                                            3 [0, 20]                       ""
    tip_check_offset_max                                            5 [0, 20]                       ""
    tip_check_random_rotation_deg                                   9 [0, 180]                      ""
    attach_min_speed                                                70 [0, 180]                     ""
    attach_to_surfaces_knife_style                                  0 [0, 1]                        ""
    hp                                                              100 [0, 200]                    "WIP WIP"
 - Privates -----------------------------
    mHasJoint                                                       0 [0, 1]                        ""

PixelSceneComponent
 - Members -----------------------------
    pixel_scene                                                     -                               "loads this pixel scene file"
    pixel_scene_visual                                              -                               "this is the colors that get used for the pixels, if empty will use material colors"
    pixel_scene_background                                          -                               "this is the background file that gets loaded, if empty won't do anything"
    offset_x                                                        0 [-30, 30]                     "how much off from the entity x,y will this be. Top left corner is where it loads the pixel scene"
    offset_y                                                        0 [-30, 30]                     ""
    skip_biome_checks                                               0 [0, 1]                        "biome check is on by default - it will check that pixel scene is loaded so that every corner is in the same biome"
    skip_edge_textures                                              0 [0, 1]                        "if on - won't do the edge textures for the pixel scene"

PixelSpriteComponent
 - Members -----------------------------
    image_file                                                      -                               "loads pixelsprite based on this file"
    anchor_x                                                        0 [0, 3.5]                      "the anchor and center_offset"
    anchor_y                                                        0 [0, 3.5]                      "the anchor and center_offset"
    material                                                        wood_loose [0, 1]               "what's the material that things are made out of, TODO - change this into MetaCustom"
    diggable                                                        1 [0, 1]                        "if 1, this can be broken with digger"
    clean_overlapping_pixels                                        1 [0, 1]                        "cleans up the pixels that are ovelapping in the world"
    kill_when_sprite_dies                                           1 [0, 1]                        "kills the entity, if the pixel sprite is dead (empty)"
    create_box2d_bodies                                             0 [0, 1]                        "if true, will create new pixel sprites with box2d bodies, instead of gridworld cells"

PlatformShooterPlayerComponent
 - Members -----------------------------
    aiming_reticle_distance_from_character                          40 [0, 1000]                    ""
    camera_max_distance_from_character                              25 [0, 1000]                    ""
    blood_healing_speed                                             0.004 [0, 1000]                 ""
    blood_drunken_speed                                             0.002 [0, 1000]                 ""
    alcohol_drunken_speed                                           0.005 [0, 1000]                 ""
    blood_fungi_drunken_speed                                       0.006 [0, 1000]                 ""
    blood_worm_drunken_speed                                        0.006 [0, 1000]                 ""
    eating_cells_per_frame                                          1 [0, 100]                      ""
    eating_probability                                              5 [0, 100]                      ""
    eating_delay_frames                                             30 [0, 100]                     ""
    stoned_speed                                                    0.1 [0, 1000]                   ""
    center_camera_on_this_entity                                    1 [0, 1]                        ""
    move_camera_with_aim                                            1 [0, 1]                        "if true, moves camera with the aim."
 - Privates -----------------------------
    mSmoothedCameraPosition                                         -                               ""
    mSmoothedAimingVector                                           -                               ""
    mCameraRecoil                                                   0 [0, 1]                        ""
    mCameraRecoilTarget                                             0 [0, 1]                        ""
    mCrouching                                                      0 [0, 1]                        ""
    mCameraDistanceLerped                                           0 [0, 1]                        ""
    mRequireTriggerPull                                             0 [0, 1]                        ""
    mWarpDelay                                                      0 [0, 1]                        ""
    mItemTemporarilyHidden                                          0 [0, 1]                        ""
    mDesiredCameraPos                                               -                               ""
    mHasGamepadControlsPrev                                         0 [0, 1]                        ""

PlayerCollisionComponent
 - Members -----------------------------
    getting_crushed_threshold                                       5 [0, 100]                      ""
    moving_up_before_getting_crushed_threshold                      3 [0, 100]                      ""
 - Privates -----------------------------
    getting_crushed_counter                                         0 [0, 1]                        "1.12.2018 - Is this still used?"
    stuck_in_ground_counter                                         0 [0, 1]                        "used this mostly for player to figure out if it's stuck in ground"
    DEBUG_stuck_in_static_ground                                    0 [0, 1]                        "used to report error + also to free the player in case something horrible has gone wrong"
    mCollidedHorizontally                                           0 [0, 1]                        ""
    mPhysicsCollisionHax                                            -                               "hax"

PlayerStatsComponent
 - Members -----------------------------
    lives                                                           1 [0, 1]                        ""
    max_hp                                                          4 [0, 1]                        ""
    speed                                                           1 [0, 1]                        ""

PositionSeedComponent
 - Members -----------------------------
    pos_x                                                           0 [0, 3.5]                      ""
    pos_y                                                           0 [0, 3.5]                      ""

PotionComponent
 - Members -----------------------------
    spray_velocity_coeff                                            1 [0, 2]                        ""
    spray_velocity_normalized_min                                   0.5 [0, 1]                      ""
    body_colored                                                    0 [0, 1]                        ""
    throw_bunch                                                     0 [0, 1]                        ""
    throw_how_many                                                  5 [0, 1]                        ""
    never_color                                                     0 [0, 1]                        "Petri: body_colored didn't seem to work, so I added never_color. It can be set to true if you never want the potion to be colored"

PressurePlateComponent
 - Members -----------------------------
    check_every_x_frames                                            30 [0, 1]                       "how often do we check the world"
    state                                                           0 [0, 1]                        "0 is up, 1 is down"
    material_percent                                                0.75 [0, 1]                     "how much material should there be in the aabbs that we go down "
 - Privates -----------------------------
    mNextFrame                                                      0 [0, 1]                        ""

ProjectileComponent
 - Members -----------------------------
    lifetime                                                        -1 [0, 1]                       "lifetime, -1 means it's endless, otherwise it's the frame count"
    lifetime_randomness                                             0 [0, 1]                        "final lifetime will be lifetime + random(-lifetime_randomness,lifetime_randomness)"
    on_lifetime_out_explode                                         0 [0, 1]                        "when lifetime runs out, should we explode?"
    collide_with_world                                              1 [0, 1]                        "true by default. Some projectiles you don't want to collide with the world, e.g. blackholes"
    speed_min                                                       60 [0, 60000]                   ""
    speed_max                                                       60 [0, 60000]                   ""
    friction                                                        0 [0, 60000]                    ""
    direction_random_rad                                            0 [0, 3.14151]                  "when fired, randomizes the velocity -this, this"
    direction_nonrandom_rad                                         0 [-3.14, 3.14]                 "when fired, multiplies this with projectile_i and adds it to direction"
    lob_min                                                         0.5 [0, 60000]                  ""
    lob_max                                                         0.8 [0, 60000]                  ""
    camera_shake_when_shot                                          0 [0, 60000]                    ""
    shoot_light_flash_radius                                        0 [0, 60000]                    ""
    shoot_light_flash_r                                             255 [0, 255]                    ""
    shoot_light_flash_g                                             180 [0, 255]                    ""
    shoot_light_flash_b                                             150 [0, 255]                    ""
    create_shell_casing                                             0 [0, 1]                        "should we create shell casings?"
    shell_casing_material                                           brass [0, 1]                    "material of the shell casing"
    muzzle_flash_file                                               -                               "this entity is created along with the projectile, oriented along the projectile's path"
    bounces_left                                                    0 [0, 1e+008]                   ""
    bounce_energy                                                   0.5 [0, 1]                      "when bouncing, velocity is multiplied by this"
    bounce_always                                                   0 [0, 1]                        "if true, will do a fake bounce if can't do the proper bounce, but will always try to bounce"
    bounce_at_any_angle                                             0 [0, 1]                        "if true, will bounce at any reflection angle"
    attach_to_parent_trigger                                        0 [0, 1]                        "if true, will attach to the projectile entity that created this projectile via a trigger"
    bounce_fx_file                                                  -                               "this entity is created at the bounce position. it gets the bounce angle as rotation."
    angular_velocity                                                0 [-3.1415, 3.1415]             "this is only applied if velocity_sets_rotation == false"
    velocity_sets_rotation                                          1 [0, 1]                        "whether we set the rotation based on velocity, as in spear or if we update the rotation with angular_velocity"
    velocity_sets_scale                                             0 [0, 1]                        "if true, the sprite width is made equal to the distance traveled since last frame"
    velocity_sets_scale_coeff                                       1 [0, 1]                        "Larger value means velocity affects the scale more"
    velocity_sets_y_flip                                            0 [0, 1]                        "if true, the sprite is flipped based on which side the projectile is currently traveling"
    velocity_updates_animation                                      0 [0, 1]                        "updates the animation based on far the sprite moved"
    ground_penetration_coeff                                        0 [0, 5]                        "this, along with VelocityComponent.mass affects how far we penetrate in materials"
    go_through_this_material                                        -                               "if set, we never collide with this material"
    on_death_duplicate_remaining                                    0 [0, 1]                        "if greater than 0, the projectile creates two clones of itself on death. 'on_death_duplicate_remaining' on the clones is reduced by one"
    on_death_gfx_leave_sprite                                       1 [0, 1]                        "if true, finds all the sprites and leaves as sand cells into the grid"
    on_death_explode                                                0 [0, 1]                        "if true, does explosion with config_explosion"
    on_death_emit_particle                                          0 [0, 1]                        "if true, emits on_death_emit_particle_type on death"
    on_death_emit_particle_count                                    1 [0, 1]                        "how many particles should we emit"
    die_on_liquid_collision                                         0 [0, 1]                        "if true, dies on collision with liquids"
    die_on_low_velocity                                             0 [0, 1]                        "if true, dies when speed goes below die_on_low_velocity_limit"
    die_on_low_velocity_limit                                       50 [0, 1]                       "please see die_on_low_velocity"
    on_death_emit_particle_type                                     -                               ""
    on_death_particle_check_concrete                                0 [0, 1]                        "if you want it to stick as concrete, you should enable this"
    ground_collision_fx                                             1 [0, 1]                        "if 1, spurt some particles when colliding with mortals"
    explosion_dont_damage_shooter                                   0 [0, 1]                        "if true, explosion doesn't damage the entity who shot this"
    on_death_item_pickable_radius                                   0 [0, 1]                        "if > 0, makes items closer than this radius pickable on death"
    penetrate_world                                                 0 [0, 1]                        "if true, the projectile doesn't collide with ground, liquids, physical objects etc"
    penetrate_world_velocity_coeff                                  0.6 [0, 1]                      "if 'penetrate_world' is true, the projectile moves with a velocity multiplied by this value when inside world"
    penetrate_entities                                              0 [0, 1]                        "if true, the projectile doesn't stop when it collides with entities. damages each entity only once"
    on_collision_die                                                1 [0, 1]                        "if true, this is killed as soon as it hits the ground"
    on_collision_remove_projectile                                  0 [0, 1]                        "if true, ProjectileComponent is removed from the entitiy"
    on_collision_spawn_entity                                       1 [0, 1]                        "if true, spawns the spawn_entity"
    spawn_entity                                                    -                               "this is spawned if hit something an on_collision_spawn_entity = 1"
    spawn_entity_is_projectile                                      0 [0, 1]                        "if true, will use ShootProjectile instead of LoadEntity()"
    physics_impulse_coeff                                           300 [0, 1]                      "projectile applies an impulse to physics bodies it hits. Impulse = physics_impulse_coeff * velocity"
    damage_every_x_frames                                           -1 [0, 1]                       "if set != -1, will only do damage every x frames, used for fields and such, which would otherwise do damage every frame"
    damage_scaled_by_speed                                          0 [0, 1]                        "if 1, damage is multiplied by (projectile speed / original projectile speed) ratio"
    collide_with_entities                                           1 [0, 1]                        "if 1, looks for entities with tag, collide_with_tag and collides with them, giving them damage"
    collide_with_tag                                                hittable [0, 1]                 "default: mortal, if you needed can be changed to something more specific"
    collide_with_shooter_frames                                     -1 [0, 1]                       "remember friendly_fire 1, if -1 won't collide with shooter at all, otherwise uses the value as frame count and while it's running won't damage the shooter "
    friendly_fire                                                   0 [0, 1]                        "if true, will damage same herd id"
    damage                                                          1 [0, 1]                        "how much Projectile damage does this do when it hits something"
    knockback_force                                                 0 [0, 1]                        "How far do entities get thrown if a knockback occurs. final_knockback = ProjectileComponent.knockback_force * VelocityComponent.mVelocity * VelocityComponent.mass / who_we_hit.mass"
    ragdoll_force_multiplier                                        0.025 [0, 1]                    "velocity * ragdoll_force_multiplier is applied to any ragdolls that are created by entities killed by this"
    hit_particle_force_multiplier                                   0.1 [0, 1]                      "hit particle velocity = projectile_velocity * hit_particle_force_multiplier * some randomness"
    blood_count_multiplier                                          1 [0, 1]                        "how much blood does this projectile cause"
    damage_game_effect_entities                                     -                               "a list of game_effects entities separated with ','. e.g. 'data/entities/misc/effect_electrocution.xml,data/entities/misc/effect_on_fire.xml' "
    never_hit_player                                                0 [0, 1]                        "If 1, does not hit player no matter what herds this and player belong to"
    collect_materials_to_shooter                                    0 [0, 1]                        "if 1, looks up the 'who_shot' entity and its MaterialInventoryComponent on destruction and updates it based on the cells destroyed on our explosion."
    play_damage_sounds                                              1 [0, 1]                        ""
    mLastFrameDamaged                                               -1024 [0, 1]                    ""
 - Objects -----------------------------
    config                                                          -                               ""
    config_explosion                                                -                               "if we have explosion, it's the setup for it"
    damage_by_type                                                  -                               "the amounts of different types of damage this does"
    damage_critical                                                 -                               "config for critical hit"
 - Privates -----------------------------
    mWhoShot                                                        0 [0, 1]                        ""
    mWhoShotEntityTypeID                                            0 [0, 1]                        "used for stats"
    mShooterHerdId                                                  0 [0, 1]                        ""
    mStartingLifetime                                               0 [0, 1]                        ""
    mTriggers                                                       -                               ""
    mDamagedEntities                                                -                               ""
    mInitialSpeed                                                   -1 [0, 1]                       ""

RainEmitterComponent
 - Members -----------------------------
    lifetime                                                        3600 [0, 1000]                  ""
    gravity_y                                                       10 [0, 10]                      ""
    droplets_bounce                                                 1 [0, 1]                        ""
    density                                                         0 [0, 3.5]                      ""
    material                                                        water [0, 3.5]                  ""
    extra_wind                                                      0 [0, 100]                      ""
    mDensity                                                        0 [0, 3.5]                      ""

RotateTowardsComponent
 - Members -----------------------------
    entity_with_tag                                                 player_unit [0, 1]              "will rotate this entity towards the closest entity with tag"

SetLightAlphaFromVelocityComponent
 - Members -----------------------------
    max_velocity                                                    50 [1, 150]                     ""
 - Privates -----------------------------
    mPrevPosition                                                   -                               ""

SetStartVelocityComponent

ShotEffectComponent
 - Members -----------------------------
    extra_modifier                                                  -                               "name of modifier function executed per projectile from 'gun_extra_modifiers.lua'"

SimplePhysicsComponent
 - Members -----------------------------
    can_go_up                                                       1 [0, 1]                        "if set, will not try to move this upwards"
 - Privates -----------------------------
    mOldPosition                                                    -                               "used for box2d simple physics"

SineWaveComponent
 - Members -----------------------------
    sinewave_freq                                                   1 [0, 1]                        "sinewave_m * sinf( sinewave_freq * lifetime++)"
    sinewave_m                                                      0.6 [0, 1]                      "sinewave_m * sinf( sinewave_freq * lifetime++)"
    lifetime                                                        -1 [0, 1]                       "-1 seems to fix some problems with this... sinewave_m * sinf( sinewave_freq * lifetime++)"

SpriteAnimatorComponent
 - Members -----------------------------
    target_sprite_comp_name                                         character [0, 1]                ""
    rotate_to_surface_normal                                        0 [0, 1]                        ""
 - Privates -----------------------------
    mStates                                                         -                               ""
    mCachedTargetSpriteTag                                          -                               ""
    mSendOnFinishedMessageName                                      -                               ""

SpriteComponent
 - Members -----------------------------
    image_file                                                      data/temp/temp_gun.png [0, 1]   ""
    ui_is_parent                                                    0 [0, 1]                        "Adds this to the GG.GetUISprite() as a child, instead of the mSpriteContainer"
    is_text_sprite                                                  0 [0, 1]                        "if you want to load a text sprite, set this to true and image_file to a font file"
    offset_x                                                        0 [-24, 24]                     ""
    offset_y                                                        0 [-24, 24]                     ""
    alpha                                                           1 [0, 1]                        ""
    visible                                                         1 [0, 1]                        ""
    emissive                                                        0 [0, 1]                        ""
    additive                                                        0 [0, 1]                        ""
    fog_of_war_hole                                                 0 [0, 1]                        "if 1, the alpha channel of this texture punctures a hole in the fog of war"
    smooth_filtering                                                0 [0, 1]                        ""
    rect_animation                                                  -                               ""
    next_rect_animation                                             -                               ""
    text                                                            -                               ""
    z_index                                                         1 [-256, 256]                   "0 = world grid, -1 = enemies, -1.5 = items in world, player = 0.6"
    update_transform                                                1 [0, 1]                        ""
    update_transform_rotation                                       1 [0, 1]                        ""
    kill_entity_after_finished                                      0 [0, 1]                        ""
    has_special_scale                                               0 [0, 1]                        "if this is set, sets special_scale_x and _y to scale"
    special_scale_x                                                 1 [0, 1]                        "this overrides the scale of the entity, if has_special_scale"
    special_scale_y                                                 1 [0, 1]                        "this overrides the scale of the entity, if has_special_scale"
    never_ragdollify_on_death                                       0 [0, 1]                        ""
 - Privates -----------------------------
    mSprite                                                         -                               ""
    mRenderList                                                     -                               ""
    mRenderListHandle                                               -1 [0, 1]                       ""

SpriteOffsetAnimatorComponent
 - Members -----------------------------
    x_amount                                                        0 [0, 5]                        ""
    x_speed                                                         0 [0, 5]                        ""
    y_amount                                                        2 [0, 5]                        ""
    y_speed                                                         2 [0, 5]                        ""
    sprite_id                                                       0 [0, 8]                        ""
    x_phase                                                         16 [0, 32]                      ""
    x_phase_offset                                                  0 [0, 1]                        ""

SpriteParticleEmitterComponent
 - Members -----------------------------
    sprite_file                                                     -                               "filepath to the sprite(s), supports the $[0-3] syntax"
    sprite_centered                                                 0 [0, 1]                        "sets the offset to the center of the image"
    sprite_random_rotation                                          0 [0, 1]                        "rotates the sprite randomly in 90 degree angles"
    render_back                                                     0 [0, 1]                        "if true, will set this particle to be behind entities (won't emit light)"
    delay                                                           0 [0, 1]                        "delay in seconds..."
    lifetime                                                        0 [0, 1]                        "lifetime in seconds..."
    additive                                                        0 [0, 1]                        "if 1, the sprites will be rendered using additive blending"
    emissive                                                        0 [0, 1]                        "if 1, the sprites will be rendered onto the emissive render target"
    velocity_slowdown                                               0 [0, 1]                        "what percent of the velocity is slowed by *dt"
    rotation                                                        0 [0, 1]                        "original rotation in rads"
    angular_velocity                                                0 [0, 1]                        "how much rotation there is in a second"
    use_velocity_as_rotation                                        0 [0, 1]                        "do we rotate the sprite based on the velocity"
    use_rotation_from_velocity_component                            0 [0, 1]                        "if set, will set the initial rotation based on the velocity component's velocity"
    use_rotation_from_entity                                        0 [0, 1]                        "if set, will 'inherit' rotation from the entity"
    entity_velocity_multiplier                                      0 [0, 1]                        "0 = doesn't use the velocity from spawning entity at all, 1 = uses all"
    randomize_position_inside_hitbox                                0 [0, 1]                        "if set, will randomize position inside the hitbox aabb"
    velocity_always_away_from_center                                0 [0, 1]                        "if set, will make the velocity's rotation always away from center of randomized aabb"
    camera_bound                                                    1 [0, 1]                        "if true, will be culled if not near the camera"
    camera_distance                                                 75 [0, 1]                       "if the distance from camera (edges) is higher than this, this will be culled"
    is_emitting                                                     1 [0, 1]                        "disable this from emitting..."
    count_min                                                       0 [0, 1]                        "how many particles do we spawn at one time"
    count_max                                                       1 [0, 1]                        "how many particles do we spawn at one time"
    emission_interval_min_frames                                    5 [0, 200]                      "how often do we emit particles"
    emission_interval_max_frames                                    10 [0, 200]                     "how often do we emit particles"
    entity_file                                                     -                               "if set, this entity is loaded to the emission position by the emitter when it emits"
 - Privates -----------------------------
    mNextEmitFrame                                                  0 [0, 1]                        ""

SpriteStainsComponent
 - Members -----------------------------
    sprite_id                                                       0 [0, 10]                       "which sprite (in the order in which they appear in the entity) are we going to stain?"
    fade_stains_towards_srite_top                                   1 [0, 1]                        "if 1, shades get less opaque near the top of the sprite"
 - Privates -----------------------------
    mTextureHandle                                                  -                               ""
    mState                                                          -                               ""

StatusEffectDataComponent
 - Privates -----------------------------
    mLastAttackingPlayerFrame                                       -99999 [0, 1]                   ""
    mStainEffectsSmoothedForUI                                      -                               ""

StreamingKeepAliveComponent
 - Members -----------------------------
    TEMP_TEMPY                                                      0 [0, 3.5]                      ""
    TEMP_TEMP_TEMP                                                  0 [0, 3.5]                      ""

TeleportComponent
 - Members -----------------------------
    target_x_is_absolute_position                                   0 [0, 1]                        "If set, target position x is in world coordinates, otherwise it's an offset"
    target_y_is_absolute_position                                   0 [0, 1]                        "If set, target position y is in world coordinates, otherwise it's an offset"
    source_particle_fx_file                                         data/entities/particles/teleportation_source.xml [0, 1] "This entity is loaded at the source position when teleportation occurs"
    target_particle_fx_file                                         data/entities/particles/teleportation_target.xml [0, 1] "This entity is loaded at the target position when teleportation occurs"
 - Privates -----------------------------
    safety_counter                                                  0 [0, 1]                        "used to keep track that we're not stuck in waiting for a pixel scene to load, that is not going to be loaded"
    state                                                           -                               ""
    teleported_entities                                             -                               ""
    source_location_camera_aabb                                     -                               ""

TeleportProjectileComponent
 - Members -----------------------------
    min_distance_from_wall                                          16 [0, 16]                      ""
    actionable_lifetime                                             3 [0, 20]                       ""
 - Privates -----------------------------
    mWhoShot                                                        0 [0, 1]                        ""

TextLogComponent
 - Members -----------------------------
    key                                                             -                               ""
    image_filename                                                  -                               ""
 - Privates -----------------------------
    mCachedName                                                     -                               ""

TorchComponent
 - Members -----------------------------
    probability_of_ignition_attempt                                 15 [0, 100]                     "how likely are we to ignite colliding cells"
    suffocation_check_offset_y                                      -2 [-10, 10]                    "check offset in world coordinates from our position"
    frames_suffocated_to_extinguish                                 5 [0, 30]                       "how many frames the torch needs to be suffocated before it stops emitting fire"
    extinguishable                                                  1 [0, 1]                        "if 1, the torch needs to be re-ignited in case it is turned off"
    fire_audio_weight                                               0 [0, 2]                        "how loud is the sound of our fire? 0 = no sound"
 - Privates -----------------------------
    mFlickerOffset                                                  0 [0, 1]                        ""
    mFramesSuffocated                                               0 [0, 1]                        ""
    mIsOn                                                           1 [0, 1]                        ""
    mFireIsBurningPrev                                              0 [0, 1]                        ""

UIIconComponent
 - Members -----------------------------
    icon_sprite_file                                                -                               ""
    name                                                            -                               ""
    description                                                     -                               ""

UIInfoComponent
 - Members -----------------------------
    name                                                            -                               ""

VariableStorageComponent
 - Members -----------------------------
    name                                                            -                               ""
    value_string                                                    -                               ""
    value_int                                                       0 [0, 1]                        ""
    value_bool                                                      0 [0, 1]                        ""

VegetationComponent
 - Members -----------------------------
    is_visual                                                       0 [0, 1]                        "the type of the tree. If is_visual=0 will insert the pixels into the world as cells. is_visual=1 will add a single cell and attach an image to that particle"
    is_real_pixels                                                  0 [0, 1]                        "if true will create the actual pixels into the world of the material given"
    is_grass                                                        0 [0, 1]                        "if set will treat this as grass and lay it on surfaces defined in material_on_top_of ( if not set will put it ontop of everything). "
    is_ceiling_plant                                                0 [0, 1]                        ""
    check_safety                                                    0 [0, 1]                        "if set, will check the 4 corners for safty"
    rand_seed                                                       1234 [0, 10000]                 "uses this to randomize the positions"
    tree_width                                                      120 [0, 512]                    "partitions the space into tree_width lengths each partion might have a tree"
    tree_radius_low                                                 0.3 [0, 1]                      "within the tree width what's the min distance it can spawn in (0) all the way to the left"
    tree_radius_high                                                0.7 [0, 1]                      "within the tree width what's the max distance (1) all the way to right"
    tree_probability                                                0.7 [0, 1]                      "what's the probability of a tree being spawned in a tree_width section"
    is_rare                                                         0 [0, 1]                        "if true, the tree is spawned only 1/3 of cases"
    tree_extra_y                                                    2 [0, 50]                       "if is_visual is true, then this will move it down by this much"
    tree_image_file                                                 -                               "filename of the png that will get loaded as the tree. The filename can have the $[1-4] notation in it"
    tree_image_visual                                               -                               "this will be used if is_visual=1, if it's not set then we will use tree_image_file"
    tree_material                                                   wood [0, 1]                     "material that the tree is made out of, or is_visual=1 then it's material that the seed is made out of"
    visual_offset_x                                                 0 [0, 1]                        "is_visual=1, will set the centerpoint (SetCenterOffset) of the image to this"
    visual_offset_y                                                 0 [0, 1]                        "is_visual=1, will set the centerpoint (SetCenterOffset) of the image to this"
    visual_color                                                    0xFFFFFF [0, 1]                 "is_visual=1, the color of the single cell that is created for the plant"
    grass_requires_neighbors                                        0 [0, 1]                        "is_grass=1, and this is set, then will check that there is a pixel to down left and down right (so it doesn't leak down)."
    material_on_top_of                                              -                               "Creates this only on top of this material, if empty then anything goes"
    height_check                                                    0 [0, 1]                        "if != 0 will check that there is air up to this height"
    max_y                                                           99999 [0, 1]                    "this is the max y that the plant / tree can be placed"
 - Privates -----------------------------
    mVisualColor                                                    0 [0, 1]                        ""
    tree_material_id                                                -1 [0, 1]                       ""
    material_id_on_top_of                                           -1 [0, 1]                       ""
    mTreeData                                                       -                               ""

VelocityComponent
 - Members -----------------------------
    gravity_x                                                       0 [0, 1]                        ""
    gravity_y                                                       400 [0, 1]                      ""
    mass                                                            0.05 [0, 10]                    ""
    air_friction                                                    0.55 [0, 1]                     ""
    apply_terminal_velocity                                         1 [0, 1]                        ""
    terminal_velocity                                               1000 [0, 1]                     ""
    updates_velocity                                                1 [0, 1]                        ""
    displace_liquid                                                 1 [0, 1]                        ""
 - Privates -----------------------------
    mLatestLiquidHitCount                                           0 [0, 1]                        ""
    mAverageLiquidHitCount                                          0 [0, 1]                        ""
    mPrevPosition                                                   -                               ""

VerletPhysicsComponent
 - Members -----------------------------
    num_points                                                      2 [0, 1]                        ""
    num_links                                                       2 [0, 1]                        ""
    width                                                           1 [0, 1]                        ""
    resting_distance                                                2 [0, 16]                       ""
    mass_min                                                        0.8 [0.03, 2]                   ""
    mass_max                                                        1 [0.03, 2]                     ""
    stiffness                                                       1 [0, 1]                        ""
    velocity_dampening                                              0.99 [0.2, 1]                   ""
    gets_entity_velocity_coeff                                      0 [0, 10]                       ""
    collide_with_cells                                              1 [0, 1]                        ""
    simulate_gravity                                                1 [0, 1]                        ""
    simulate_wind                                                   1 [0, 1]                        ""
    wind_change_speed                                               1 [0, 1]                        ""
    constrain_stretching                                            0 [0, 1]                        ""
    pixelate_sprite_transforms                                      1 [0, 1]                        ""
    scale_sprite_x                                                  1 [0, 1]                        ""
    follow_entity_transform                                         1 [0, 1]                        ""
    animation_amount                                                2 [0, 1]                        ""
    animation_speed                                                 5 [0, 1]                        ""
    animation_energy                                                0.6 [0, 1]                      ""
    cloth_sprite_z_index                                            1 [0, 1]                        ""
    stain_cells_probability                                         0 [0, 1]                        "0 = never, 1 = most likely, 10 = less likely - and so on"
    m_is_culled_previous                                            0 [0, 1]                        "Developer note: this needs to be serialized in case we serialize SpriteComponent.is_visible"
 - Privates -----------------------------
    masses                                                          -                               ""
    positions                                                       -                               ""
    positions_prev                                                  -                               ""
    velocities                                                      -                               ""
    dampenings                                                      -                               ""
    freedoms                                                        -                               ""
    links                                                           -                               ""
    sprite                                                          -                               ""

VerletWeaponComponent
 - Members -----------------------------
    damage_radius                                                   5 [0, 10]                       ""
    physics_force_radius                                            3 [0, 10]                       ""
    damage_min_step                                                 0.01 [0, 3.5]                   ""
    damage_max                                                      1 [0, 3.5]                      ""
    damage_coeff                                                    1 [0, 3.5]                      ""
    impulse_coeff                                                   1 [0, 3.5]                      ""
    fade_duration_frames                                            10 [0, 100]                     ""
    physics_impulse_coeff                                           1 [0, 3.5]                      ""

VerletWorldJointComponent
 - Members -----------------------------
    verlet_point_index                                              0 [0, 32]                       "Index of the verlet point we attach"
 - Privates -----------------------------
    mUpdated                                                        0 [0, 1]                        ""
    mCell                                                           -                               ""

WalletComponent
 - Members -----------------------------
    money                                                           0 [0, 10000]                    ""
    money_spent                                                     0 [0, 1]                        "tracks how much money the player has spent"
    mMoneyPrevFrame                                                 0 [0, 1]                        "HAX to give player towards infinite moneys"
    mHasReachedInf                                                  0 [0, 1]                        "once it hits this value... keep it there"

WalletValuableComponent
 - Members -----------------------------
    money_value                                                     10 [0, 100]                     ""

WorldStateComponent
 - Members -----------------------------
    is_initialized                                                  0 [0, 1]                        ""
    time                                                            0 [0, 1]                        ""
    time_total                                                      0 [0, 1000]                     ""
    day_count                                                       0 [0, 3.5]                      ""
    rain                                                            0 [0, 1]                        ""
    rain_target                                                     0 [0, 1]                        ""
    rain_material                                                   water [0, 1]                    ""
    fog                                                             0 [0, 1]                        ""
    fog_target                                                      0 [0, 1]                        ""
    intro_weather                                                   0 [0, 1]                        "if set, will set the weather to be nice all the time"
    wind                                                            0 [0, 1]                        ""
    wind_speed                                                      2 [-50, 50]                     ""
    wind_speed_sin_t                                                10 [0, 1]                       ""
    wind_speed_sin                                                  3 [-50, 50]                     ""
    clouds_01_target                                                0 [-27, 100]                    ""
    clouds_02_target                                                0 [-100, 185]                   ""
    gradient_sky_alpha_target                                       0 [0, 1]                        ""
    sky_sunset_alpha_target                                         1 [0, 1]                        ""
    lightning_count                                                 0 [0, 100]                      "this gets decreased to 0, this is the frame count of how many times do we do our awesome lightning effect"
    endgame_location                                                0 [0, 2]                        ""
    tutorial_symbol                                                 0 [0, 51]                       ""
    next_normal_symbol_index                                        0 [0, 51]                       ""
    next_endgame_symbol_index                                       0 [0, 51]                       ""
    endgame_stage                                                   0 [0, 1]                        ""
    next_portal_id                                                  1 [0, 1]                        ""
    session_stat_file                                               -                               "if empty, we'll create one. This tracks the play time, death, kills... etch"
    player_polymorph_count                                          0 [0, 1]                        "how many times player has been polymorphed"
    player_polymorph_random_count                                   0 [0, 1]                        "how many times player has been random polymorphed"
    global_genome_relations_modifier                                0 [0, 1]                        "Genome_GetHerdRelation adds this value to the results. 100 = good relations, 0 is bad "
    mods_have_been_active_during_this_run                           0 [0, 1]                        ""
    EVERYTHING_TO_GOLD                                              0 [0, 1]                        "if true everything will be gold + used to track if the wallet should go to infinite"
    INFINITE_GOLD_HAPPENING                                         0 [0, 1]                        "the secret ending with infinite gold"
    DEBUG_LOADED_FROM_AUTOSAVE                                      0 [0, 1]                        "how many times have loaded from autosaves"
    DEBUG_LOADED_FROM_OLD_VERSION                                   0 [0, 1]                        "how many times have we loaded from an old version of the game"

WormAIComponent
 - Members -----------------------------
    speed                                                           1 [0, 10000]                    ""
    speed_hunt                                                      3 [0, 10000]                    ""
    direction_adjust_speed                                          1 [0, 10000]                    ""
    direction_adjust_speed_hunt                                     1 [0, 10000]                    ""
    random_target_box_radius                                        512 [0, 10000]                  ""
    new_hunt_target_check_every                                     30 [0, 10000]                   ""
    new_random_target_check_every                                   120 [0, 10000]                  ""
    hunt_box_radius                                                 512 [0, 10000]                  ""
    cocoon_food_required                                            30 [0, 1]                       "how much food do we need to consume before we can cocoon"
    cocoon_entity                                                   -                               "if empty, won't cocoon, if set it'll spawn this after it's eaten enough"
    give_up_area_radius                                             50 [0, 10000]                   ""
    give_up_time_frames                                             300 [0, 10000]                  ""
    debug_follow_mouse                                              0 [0, 1]                        ""
 - Privates -----------------------------
    mRandomTarget                                                   -                               ""
    mTargetEntityId                                                 0 [0, 1]                        ""
    mNextTargetCheckFrame                                           0 [0, 1]                        ""
    mNextHuntTargetCheckFrame                                       0 [0, 1]                        ""
    mGiveUpStarted                                                  0 [0, 1]                        ""
    mGiveUpAreaMinX                                                 0 [0, 1]                        ""
    mGiveUpAreaMinY                                                 0 [0, 1]                        ""
    mGiveUpAreaMaxX                                                 0 [0, 1]                        ""
    mGiveUpAreaMaxY                                                 0 [0, 1]                        ""

WormAttractorComponent
 - Members -----------------------------
    direction                                                       1 [-1, 1]                       "1 = attracts worms, -1 detracts worms"
    radius                                                          50 [0, 100]                     "radius of detracting worms"

WormComponent
 - Members -----------------------------
    speed                                                           1 [0, 10000]                    ""
    acceleration                                                    3 [0, 10000]                    ""
    gravity                                                         3 [0, 10000]                    ""
    tail_gravity                                                    30 [0, 10000]                   ""
    part_distance                                                   10 [0, 10000]                   ""
    ground_check_offset                                             0 [0, 10000]                    ""
    hitbox_radius                                                   1 [0, 1e+006]                   ""
    bite_damage                                                     1 [0, 10]                       "how much damage does this do when it hits an entity"
    target_kill_radius                                              1 [0, 1e+006]                   ""
    target_kill_ragdoll_force                                       1 [0, 1e+006]                   ""
    jump_cam_shake                                                  4 [0, 10000]                    ""
    jump_cam_shake_distance                                         256 [0, 10000]                  ""
    eat_anim_wait_mult                                              0.05 [0, 10000]                 ""
    ragdoll_filename                                                -                               ""
    is_water_worm                                                   0 [0, 1]                        "if true, tries to stay in liquids"
    max_speed                                                       25 [0, 1]                       "max speed, used when attracted to a point"
 - Privates -----------------------------
    mTargetVec                                                      -                               ""
    mGravVelocity                                                   0 [0, 1]                        ""
    mSpeed                                                          0 [0, 1]                        ""
    mTargetPosition                                                 -                               ""
    mTargetSpeed                                                    0 [0, 1]                        ""
    mOnGroundPrev                                                   0 [0, 1]                        ""
    mMaterialIdPrev                                                 0 [0, 1]                        ""
    mFrameNextDamage                                                0 [0, 1]                        ""
    mDirectionAdjustSpeed                                           1 [0, 1]                        ""

WormPlayerComponent
 - Privates -----------------------------
    mPrevPosition                                                   -                               ""
    mDirection                                                      -                               "if mDirection == 0,0 nothings works"

